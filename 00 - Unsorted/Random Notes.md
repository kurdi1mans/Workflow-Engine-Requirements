- It is obvious from the evaluation of many workflow engines that almost all of theme are built with a certain opinionated approach.
	- This is not a bad thing, but it is a limitation.
	- Out-Of-The-Box (OOTB) applications are provided as a preset feature that cannot be modified or extended.
	- A better approach is to build these OOTB applications with the design capabilities of the system itself so that the user can modify or extend the OOTB applications.
	- Moreover, in order to properly define the needed functionality and address any design shortcomings, the designers and developers of the application must build many applications (of varying complexity) using the system by themselves.
		- This will allow theme to full understand the limitations and capabilities of the system they are building.

- What seems to be the overall goal here is to build a platform that permits building complex applications with no-code.
	- This is more like switching from written code to visual coding.
	- Also, this approach relies on pre-built components that can be reused like libraries and stable patterns.

- All design artifacts must be dealt with as Data. This ensures that the workflow engine is extensible and simple. It eliminates any redundancy.
	- Register definition is data
		- already covered in the primary core tables
	- Workflow Steps, Actions, Validations, Status is data
		- required special core tables
	- Group definition is data
		- requires special core tables
	- Privilege definition is data

- Its notable how the perfect Software Requirements Specifications (SRS) document can lead to a substandard solution.
	- This is due to the fact that Software Requirements usually come from Business People. Business People are always focused on a problem domain and cannot think of extensibility and reuse.
	- Suppose that you gather requirements from multiple business departments with extremely different requirements
		- Then, you write a new SRS document for a generic solution that can cover all of these needs
		- The requirements of this new SRS document will naturally contain design aspects at a very high level as it is being written by technical people who are thinking about technical artifacts that will be used to address many business scenarios

- Its notable that as I write the requirements document, I inevitably step into the design stage.
	- This is due to the fact that an early understanding of the design influences the way requirements are written
		- For example, here is a detailed chronology of the case with access control of form fields by workflow step
			- initially, the access control for form fields was not clear due to the fact that access should be different at different Steps
			- it was not clear how access can be controlled by step making some fields required, others readable, restricting access of read and write by different groups by Steps
			- eventually, a solution was proposed to handle that in multiple different ways that are all aligned with variant-based access control
			- it became obvious that no specific requirements are actually needed to control access of fields at different workflow steps if the step is just another variant
			- However, it is actually notable that in order to properly control access of fields at different workflow steps, a methodical way of defining the variants is needed
			- This essentially means that the primary variant-based access control has the capabilities to deal with all the requirements of access of fields by workflow steps
			- However, the capabilities are very flexible and cause confusion necessitating a rigid and methodical layer of access definition to define access clearly
