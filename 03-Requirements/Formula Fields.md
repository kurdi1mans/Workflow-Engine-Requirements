Tags:: [[Requirements]],[[Data-Types]],[[Logic]]
_________________
- The system must allow for fields to have formula
	- The system must allow for bi-directional formulas
		- 2 fields (or more) all have formula
		- input values in first n fields, the last will be calculated by the formula
		- the oldest updated field will be set to formula if a new field is updated manually
		- Example
			- If the user provides a date on the Gregorian Calendar, the equivalent Hijri date is auto-calculated.
				- If the user provides a date on the Hijri Calendar, the equivalent Gregorian date is auto-calculated.

- Formulas can have any of the following logic
	- Arithmetics: +,-,*,/,^,log ... etc
	- logical operators such as: and, or, not, xor, xnor ... etc
	- if conditions such as: if, else if, else
	- conditionals such as >,<,>=,<=,=,!= ... etc
	- Date arithmatics and conditionals
	- String operations: substring, concatenate, split ... etc
	- Lookup fields
	- Rollup fields (for lineitems/sub-records)
		- Rollup fields must allow for manual data entry at leaf-level while they aggregate at higher levels based on formulas
		- Rollup fields should also allow for partialing values of an item to its children items if children items are to be added.
			- The partialing can follow a formula (uniform or based on weight of field or others)
			- The partialing can also be modified manually similar to the bi-directional formulas
		- Further analysis of the requirements and design of rollup fields is needed !!
	- Ideally, formualas must cover everything that can be used in an Excel/Google/Libre sheet.
