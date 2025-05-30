Tags:: [[Requirements]],[[Un-Categorized]]
_________________
- The system must provide the capability to create wizards
	- This is needed for a guided record creation
	- This is needed to guide action and updates on records at a workflow step

- The system must be designed to allow for offline operations
	- This is required to cover scenarios where operations are required in areas where internet availability is intermittent or non-existent

- The system must be designed to allow for bi-directional mirroring between multiple instances of itself



- Record Versioning
	- The system must provide versioning for records
	- This versioning capability must be tied to the auditing capability.

- Draft Records and Draft changes
	- Draft Records (to be created)
	- Draft Changes

- The workflow engine must keep track of the history of Workflow Action, Update, Read operations done on a record.
- The workflow engine must provide an audit log for records that include read, write, and delete operations at field-level for the records.
	- This is also part of the versioning capability.


- The system must provide automatic translation capability with the option to revise the translated text for everything in the system.
	- This functionality must be support by AI/ML models that can handle multiple languages.
- The system must provide a federated search capability that searches across all records and attached files in the system.
- The system must support multiple languages.
- The system must provide the capability to change the view from LTR to RTL for Arabic Support.


- All URLs/links in the system must be shareable, long-lasting, and reachable if the user has the proper access.
- The system must provide cell URLs such that the user can share a link to point out a specific cell in a record.

- The system must provide real-time (multiplayer) collaboration capability.
