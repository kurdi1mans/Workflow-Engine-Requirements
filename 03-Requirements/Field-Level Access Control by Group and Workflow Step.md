Tags:: [[Requirements]],[[Cybersecurity]],[[Access-Control]],[[Workflow]]
Order:: 3
_________________
- Below are two suggested approaches to deal with field-level access control by workflow step and group/role:

- The system must allow the user to define field-level access for each role/group by step
	- example
		- Role: Finance Manager
			- field:Classification - editable - Step:<all>
			- field:Salary - editable - Step:Revision
			- field:record_no - view - Step:<all>
			- field:Job_Title - editable - Step:Revision
		- Role: Project Manager (the requester who initiates the workflow)
			- field:Classification - editable - Step:<all>
			- field:Salary -- no permission assigned (user cannot see this field or modify it)
			- field:record_no - view - Step:<all>
			- field:Job_Title - editable - Step:Revision
- These same permission can be managed using a step-based perspective which is similar to the classical approach of access control in workflow engines
	- example: show the same permission by step-first (still has specification by group/role)
		- Step: Initiation
			- Role: Finance Manager
				- field:Classification - editable
				- field:Salary - editable
				- field:record_no - view
				- field:Job_Title - editable
			- Role: Project Manager
				- field:Classification - editable
				- field:Salary -- no permission assigned
				- field:record_no - view
				- field:Job_Title - editable
		- Step: Revision
			- Role: Finance Manager
				- field:Classification - editable
				- field:Salary - editable
				- field:record_no - view
				- field:Job_Title - editable
			- Role: Project Manager
				- field:Classification - editable
				- field:Salary -- no permission assigned (cannot see this field or modify it)
				- field:record_no - view
				- field:Job_Title - editable
	- example: set permission for step without group/role specifications (similar to the classical approach of access control at step level)
		- Step: Initiation
			- field:Classification - editable
			- field:Salary - editable
			- field:record_no - view
			- field:Job_Title - editable
		- Step: Revision
			- field:Classification - editable
			- field:Salary - editable
			- field:record_no - view
			- field:Job_Title - editable

- In general, these 4 variants of access can be viewed/modified in multiple perspectives similar to a pivot table
	- Role then field then access then step
	- Step then role then field then access
	- Step then field then access without role (classical approach)
	- others
- Access control can be set at the field level using one of these access types
	- View-Only
	- Editable
	- Editable-Required
	- Hidden
- Should we allow defining the field-level access control by more variants (other than the established 4 Role, Field, Step, Access)??
	- This might be necessary to allow for more flexibility to address the non-standard requirements of multiple organizations for the same process
	- Alternatively, different workflows and forms might need to be designed for different organizations
