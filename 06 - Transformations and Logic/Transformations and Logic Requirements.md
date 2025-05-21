
- The system must provide the capability to transform data using complex logic similar to SQL
	- This transformation mechanism must cache results as per a push-based, deltified, transactional mechanism
	- The references to datafields must be by ID rather than name in order to allow for renaming of fields and tables.
	- The result of these transformations can either be additional columns in the register/sheet or a new register/sheet that serves as a view of the primary register/sheet.


- One primary mechanism to build the data transformation capability is the Deltified Transformation logic
	- This means that any calculations that uses data from the source must not be fully recomputed if there is a way to shortcut the calculation using some delta-logic.
		- example, calculating the average salary for all employees might require summing all salaries then dividing by the count
			- Alternatively, the total and count might be stored permanently and updated everytime a change happen to employee salaries to generate the new average based on the below formulas:
				- New Total = Old Total +/- Change
				- New Count = Old Count +/- Change
		- This concept of logic deltification requires further study to determine its feasibility.


- One main problem with SQL dataviews is the fact that
	- SQL references artifacts (tables, views, and columns) by name (not ID)
		- This essentially means that renaming any column or table will break the SQL code
	- SQL dataviews are not cached by default
		- This means that everytime a dataview is queried, the logic is executed again which causes performance issues.
		- If dataviews are to be materialized (cached) to improve performance, it has to happen as per a scheduled frequency.
			- This means there is a risk of jeopardizing data integrity as the materialized dataview can be outdated. Outdated data is not reliable if robust transactions are needed.
	- SQL dataviews are pull-based
		- The logic is executed when needed.
		- The result is not cached. Moreover, even if cached, it's not reliable as it is not up-to-date.
		- A mechanism is needed to cache the result and refresh it (transactionally) when a change happens using push-based deltified logic to ensure better performance.
