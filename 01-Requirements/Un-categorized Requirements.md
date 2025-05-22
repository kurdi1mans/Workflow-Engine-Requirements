---
tags:
  - Requirements
---
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
