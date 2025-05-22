---
tags:
  - Requirements
---
- The system must provide the capability to control access at field-level based on workflow step, group/role, field
- The system must provide the capability to control the flow of the workflow as per the principals of Role-Based Access Control
- The system must provide the capability to control access to records as per the principals of Variant-Based Access Control
- The system must allow the user to create his own sheets
- Workflow steps can have assigned groups
	- Records can be sent to a step even if the assigned group has no members
	- At any point of time, if a user is added to a group, the tasks at that step will be available to the user for action

- The system must provide Audit Logs
	- Audit logs must cover all operations on the system (Read, Write, Delete)
	- All Operations must be provided at the lowest level possible (field-level)

- For sensitive fields shown as part of a long register, read operations cannot be effectively tracked
	- a Solution here is to set the value of the field invisible
		- Users can un-hide the value of each cell separately (generating an audit log item)

- The system must provide the capability for external collaborators to create/modify records download/upload files.
	- public users (submit complaints, tickets, inquiries)
	- password
	- Restricted to email domain
	- Restricted to specific email addresses or phone numbers
		- authenticated through tokens sent to email or phone numbers

- The system must provide the capability to restrict access to specific IPs or IP ranges for groups of Users.
- The system must provide MFA capability that can be configured by Admins.
- The system must provide the capability to restrict session time, session timeout.



- The system must provide functionality to provide digitally signed documents
	- This functionality must also allow integration with 3rd party service providers
		- A third party service provider can play the role of a witness in this case. Therefore, even if the system provides this capability, the use of third-party vendor might still be required.
