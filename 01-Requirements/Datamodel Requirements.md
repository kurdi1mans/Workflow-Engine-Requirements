---
tags:
  - Requirements
---
- Fields Definition
	- Field Names can be changed
		- How will dataviews deal with name changes??



- A point that is yet to be addressed in the design is the fact that different organizations (think Offshore Projects vs Onshore Projects in a Giant Oil Company) might requires slightly different fields for the same Process.
	- For example, Offshore projects involves working on Offshore Rigs which might require additional fields specific to this special case of working environment.
	- In general, fields might differ based on certain criteria related to Geography, Domain, Industry, ... etc.
	- Remember the case of the 21 different departments that were struggling to standardize their processes due to sheer variance in their nature and requirements.
	- A more specific example that I can recall is the funding mechanism for Offshore Projects.
		- The budgeting/funding mechanism was appropriation-based due to the fact that Offshore Oil-Field Projects were more of giant iterations of an operation rather than project with a unique scope. They have to be dealt with as projects due to the sheer size. However, the funding mechanism is appropriation-based rather than budget-based due to the operation-like nature of these projects.
	- Should these be implemented as separate processes??
	- Should these be implemented as a single process with different field-level access control setups by an organization variant??



- The system must allow for merging records in the same register/sheets
- The system must allow for merging registers/sheets
	- This is necessary as you might need multiple registers/sheets to model the as-is business of different organizations. Then, you might need to merge these registers/sheets (as part of the standardization process) according to the to-be business model.

- The system must allow for splitting registers/sheets

- The system must allow for cloning records
- The system must provide drag-fill functionality for cells




- Consider the following scenario
	- you have a register/process for surveys
	- Based on a drop down, you have multiple types of surveys
	- Each type of survey will have a different set of questions that should appear on the form of the process
	- If you have 100 types of surveys and the questions for each type are different fields
	- storing these as columns is going to be insane because you could have up to a thousand five thousand columns
	- so how can we somehow store upper form fields, we store them as line items?
		- This can be solved if the datamodel itself is built to store columns as rows in some other registry, thereby allowing an infinite number of columns
