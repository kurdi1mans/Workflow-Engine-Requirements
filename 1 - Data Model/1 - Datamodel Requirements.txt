- Fields Definition
	- Field Names can be changed
		- How will dataviews deal with name changes??




- The system must allow for fields to have formula
	- The system must allow for bi-directional formulas
		- 2 fields (or more) all have formula
		- input values in first n fields, the last will be calculated by the formula
		- the oldest updated field will be set to formula if a new field is updated manually
		- Example
			- If the user provides a date on the Gregorian Calendar, the equivalent Hijri date is auto-calculated.
				- If the user provides a date on the Hijri Calendar, the equivalent Gregorian date is auto-calculated.

- Formulas can have any of the following logic
	- Arithmetics: +,-,*,/,^,log ... etc
	- logical operators such as: and, or, not, xor, xnor ... etc
	- if conditions such as: if, else if, else
	- conditionals such as >,<,>=,<=,=,!= ... etc
	- Date arithmatics and conditionals
	- String operations: substring, concatenate, split ... etc
	- Lookup fields
	- Rollup fields (for lineitems/sub-records)
		- Rollup fields must allow for manual data entry at leaf-level while they aggregate at higher levels based on formulas
		- Rollup fields should also allow for partialing values of an item to its children items if children items are to be added.
			- The partialing can follow a formula (uniform or based on weight of field or others)
			- The partialing can also be modified manually similar to the bi-directional formulas
		- Further analysis of the requirements and design of rollup fields is needed !!
	- Ideally, formualas must cover everything that can be used in an Excel/Google/Libre sheet.


- Versions and Drafts
	- The system must provide versioning for records
	- This versioning capability must be tied to the auditing capability.

- The workflow engine must keep track of the history of Workflow Action, Update, Read operations done on a record.
- The workflow engine must provide an audit log for records that include read, write, and delete operations at field-level for the records.
	- This is also part of the versioning capability.




- A point that is yet to be addressed in the design is the fact that different organizations (think Offshore Projects vs Onshore Projects in a Giant Oil Company) might requires slightly different fields for the same Process.
	- For example, Offshore projects involves working on Offshore Rigs which might require additional fields specific to this special case of working environment.
	- In general, fields might differ based on certain criteria related to Geography, Domain, Industry, ... etc.
	- Remember the case of the 21 different departments that were struggling to standardize their processes due to sheer variance in their nature and requirements.
	- A more specific example that I can recall is the funding mechanism for Offshore Projects.
		- The budgeting/funding mechanism was appropration-based due to the fact that Offshore Oil-Field Projects were more of giant iterations of an operation rather than project with a unqiue scope. They have to be dealth with as projects due to the sheer size. However, the funding mechanism is appropriation-based rather than budget-based due to the operation-like nature of these projects.
	- Should these be implemented as separate processes??
	- Should these be implemented as a single process with different field-level access control setups by an organization variant??



- The system must allow for merging records in the same register/sheets
- The system must allow for merging registers/sheets
	- This is necessary as you might need multiple registers/sheets to model the as-is business of diffferent organizations. Then, you might need to merge these registers/sheets (as part of the standardization process) according to the to-be business model.
- The system must allow for cloning records
- The system must provide drag-fill functionality for cells



- Some data types are just specific form of other data types.
+ For Example, phone number (+966-5-12345678) is a restricted type of String. The same applies to emails.

- What other data types?
+ Video
+ File
+ Code
+ Image


- I should not worry about the datatypes in the database as they are very limited
- What I should worry about is the different types of fields as per the way they are visualized on the front-end and their behavior.
	- Then, the secondary concern is how they are similar to each other.


- Consider the following scenario
	- you have a register/process for surveys
	- Based on a drop down, you have multiple types of surveys
	- Each type of survey will have a different set of questions that should appear on the form of the process
	- If you have 100 types of surveys and the questions for each type are different fields
	- storing these as columns is going to be insane because you could have up to a thousand five thousand columns
	- so how can we somehow store upper form fields, we store them as line items?
		- This can be solved if the datamodel itself is built to store columns as rows in some other registry, thereby allowing an infinite number of columns
