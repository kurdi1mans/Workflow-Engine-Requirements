---
tags:
  - Requirements
---

- The workflow engine must be built as a JavaScript library.

- The library must provide functions to create its own datamodel inside a database as per the developers choosing
	- The developer might choose a separate database for the datamodel of the library
	- The developer might choose a separate schema for the datamodel of the library

- The System must provide idempotent APIs/Operations wherever applicable.