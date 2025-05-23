Tags:: [[Requirements]],[[Display]]
_________________
- The library must provide functions to create/modify/delete Forms
	- Forms must contain blocks
	- Blocks contain fields
	- What fields will be read-only, editable, or required is not the concern of the functionality of form management
	- fields
		- field can auto-populate from other records
			- there has to be an option for specify if the auto-population is live, dead-on-arrival, or dead-on-condition
	- views for the logs of the records

- Custom Prints
	- The system must provide the capability to create custom prints
	- Custom prints must be built with blocks similar to forms
	- Design of blocks must be generic and reusable
	- Blocks must be dynamic as per the data it receives
	- Custom prints must allow exporting to Excel, Word, PDF ... etc.

- Another Shortcoming in Unifier is the use of Custom Prints
	- Custom Prints is merely a different design for the view of the record
	- They are simply a different form design that is more print-friendly.

- Different Data Structures
	- Lineitems
		- can be stored as separate records
	- Tables
		- can be stored as separate records
	- Trees (hierarchies)
		- can be stored as records in the same register with parent-child relationships
	- Graphs
		- can be stored as records with relationships
			- can either be primary records or lineitem records (if multiple graphs are needed)
			- nodes can be stored in a register while edges can be stored in another register
	- Flowcharts (workflow charts)
		- a specific type of graphs
		- Should also be the primary type of data structure to store the workflow designs
	- Swimlane diagrams
		- a specific type of flowchart with lanes for group assignments
	- Mindmaps
	- Maps (interactive maps)
		- pins, lines, polygons
		- can be stored as separate recordsم
	- Pivot Table
	- Email Threads
		- can be stored as separate records

- Different Views/Displays
	- Hierarchical/Tree
	- Table in Record
		- The table view must provide conditional formatting capability similar to Excel
	- Tab with lineitems
	- Graph
	- Flowchart
	- Swimlane
	- Mindmap
	- Maps
	- Pivot Table
	- Email Thread
		- Zoho Desk like view
			- View can be set to show the record field on the side
			- The main body of the record shows email threads
	- Gantt Chart


- The system must provide alternate views for the register/sheet
	- For example, if I want to view the record like a ticketing system (say Zoho Desk), the fields of the record should be shown on the side.
- The system must provide multiple options for view of the log of the register/sheet
	- examples
		- view as Zoho Desk
		- view as Excel Sheet
		- View as Unifier
		- View as Tree
		- View as Graph
		- View as Pivot Table
		- View as Gantt Chart
