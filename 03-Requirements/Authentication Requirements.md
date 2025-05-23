Tags:: [[Requirements]],[[Cybersecurity]],[[Authentication]]
Order:: 1
_________________
- The system must implement authentication that is compliant with the latest approved OAuth Standard issued by the Internet Engineering Task Force (IETF). 

- The system must incorporate JWT in the Authentication mechanism.
- JWTs issued by the system for Authentication must include the below details to further improved security
	- IP address
	- User-Agent details
	- User Time-Zone
	
- The system must provide Multi-Factor Authentication

- The system must give the Admin the privilege to enable and/or require MFA for users
	- To be determined by variants (similar to the principals of Variant-Based Access Control)

- The system must provide Single-Sign-On capability.
