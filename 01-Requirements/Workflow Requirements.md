---
tags:
  - Requirements
---
- Note that Workflow Actions are not the same thing as actions.

- Workflow Steps
	- Steps
	- Workflow Actions (simialr to Termporal signals)
		- Workflow Actions are the action taken by users or external systems at a workflow step.
		- Workflow Actions determine the next workflow step.
		- A Workflow Action on a record is an update to a field that can trigger activities
	- Activities
		- Activities are operations, functions, or code that is executed automatically at a specific workflow step.
		- Activities can do automated work such as
			- run API functions
			- run certain actions within the system
		- Activities are triggered by a record arriving at a workflow step or when an action on a record is taken
		- Activities can be executed in one of two modes
			- Synchronous (Blocking)
			- Asynchronous (Non-Blocking)
		- Activities triggered by a workflow action can used for transactional validation. Therefore, they must be Synchronous and transactional.
		- Activities triggered at a workflow step must provide the following
			- Update or create other records
				- must allow access to the source record data (before and after the action)
			- send emails
			- run integrations
			- Exponential Back-Off
			- Rate Limiting
			- ... etc
	- Validations
		- Validations must be defined at action-level. In other words, the validation for each action at a specific workflow step cn be different.
			- For example, at an invoice approval step, if the action is to approve the invoice the remaining budget must be validated. However, if the invoice is to be rejected, this validation is not necessary.
		- validations must be action specific. For example, if the selected action is to reject the record, there is no need to verify anything.
		- Validations are activities that are executed as synchronous transactions that determine if an action is allowed or not.


- Workflow definition is data stored in a register
	- Step definition is data
	- Validation definition is data
	- Workflow Actions are stored as data
	- Workflow State definition is data
	- Data related to what workflow step the record is at (Workflow State) must be kept as a register
		- This way it can be updated moving a record from a step to another.
		- This change can be handling through a workflow to obtain the required approvals


- Dynamic Workflow Paths (approval paths changes based on record type or RPO)
- Workflow engine must provide the capability to have dynamic workflow approval paths
	- Sometimes the approvals required for a certain document are not fixed in terms of number of approvers. The workflow engine must allow for an approval path with a dynamic length.
	- This requirement can potentially be addressed by a circular update to the same step that relies on metadata to determine the next approver.
	- Another alternative here is to have a dynamic workflow Paths that is determined based on the content of the record itself
		- The length of the path is determined at runtime

- Transactional Processing
	- The system must allow for transactional processing
		- What kind of transactional processing??
			- Regular Single-Phase Commit Transactions
			- Two-Phase Commit or Multi-Phase Commit Transactions
			- Saga Pattern

- The system must allow for a balance-sheet like functionality
	- Similar to SOV in Unifier
	- Similar to a booking calendar in a reservation calendar
	- Similar to seat availablity on air-plane seat reservation
	- Similar to seat availablity on cinema seat reservation
	- This requires transactional processing in order to avoid conflicts


- The system must somehow provide a mechanism to identify resource availablity.
	- For example, if a user is trying to book a room, the system must provide a mechanism to check if the room is available.
	- Another example, if an employee is on leave, the system must provide a mechanism to reassign his work to someone else.
		- Access control alone is not sufficient for this.
	- These two examples pertain to two different parts of the requirements.
		- one is related to access control
		- the other is related to resource availability
		- other examples like SOV, Booking Calenders, Budget control
		- Most of these examples are specifically concerned about the availability of a certain resource.
		- However, we should also think about think about this functionality in terms of mutual exclusion or as a locking mechanism.


- The system must provide the capability to allow multiple data entries or decisions on tasks
	- For example, if the task is to enter an estimate value, the system must capture different values entered by multiple people which can later be used to assess the quality of the estimate or have multiple estimates for the same task.
	- This requirement might require certain considerations in the datamodel design.
	- This can potentially be implemented as a seperate Process with a seperate workflow (maybe sub-worflow)
	- Tasks in this case can be also be terminated if they are no longer relevant.

- The system must provide the capability to take decisions on workflow tasks according to the below approaches
	- Single Action (one assignee takes action)
	- Majority
	- Consensus

- If at any point it's deemed necessary to build automation capability similar to the one provided by AirTable, the option to access values from records before/after action is needed.
	- This is necessary due to the fact that certain automations require the value from the record before the action was taken.
		- For example, removing the assigned parent of a task requires updates to remove the current task from the parent's children list.

- The system must provide warnings for workflow steps that have no active members
	- Members can be regular users or system users (for Workflow Actions taken by external systems)


- The system must provide the capability of automatic unlocking for tasks held by users with no action
- The system must provide the capability of automatic reassignement if employee is on leave
- The system must provide the capability of automatic escalation if duration is exceeded
