# Python Numbers
TAGS: #Python 
BUILT-ON: [[Python Datatypes]]
ENABLES: - 
PREREQUSITIES: - 

---
## Numbers
~={cyan}***Immutable datatype***=~ that is used to handle numeric values in Python.
Python provides several numeric types, with the two most important ones being:
- ``int``: All real Integer numbers
- `float`: All real floating-point numbers
~={purple}***Integers***=~
- All integers are whole numbers without a fractional component. 
- Python integers can represent arbitrarily large integers, subject to available memory.
- Users don't specify the size of the integer manually, this differs from languages where integer types have fixed sizes such as 32-bit or 64-bit integers.
~={purple}***Floating-Point Numbers***=~
- All floating-point numbers represent real numbers with a fraction component.
- Floating-point is an ***approximation-oriented numeric representation***, not exact decimal arithmetic. This is because floating-point numbers are represented by using a finite binary representation and many decimal fractions cannot be exactly represented.

#### Arithmetic Operations
Python provides standard arithmetic operators.
- Addition Operator ( + )
- Subtraction Operator ( - )
- Multiplication Operator ( \* )
- Division Operator ( \/ )
- Floor Division Operator ( \// )[^1]
- Remainder/Modulo Operator ( % )
- Exponentiation Operator ( \*\* )

#### Operator Precedence
Python follows the following operator precedence when multiple operators are used in an expression:
- Parenthesis
- Exponentiation
- ``+VARIABLE`` Unchanged, `-VARIABLE` Negation
- Multiplication, Division, Floor Division, Modulo
- Addition, Subtraction

#### Numeric Functions
- ~={purple}Round Function=~: The round function is used for rounding-off a number to a certain number of decimal places. 
  `round(NUMBER/VARIABLE, PLACES)`
- ~={purple}Absolute Function=~: The absolute function is used to get the magnitude of a numeric number.
  `abs(NUMBER)`
- ~={purple}Power Function=~: The power function is an alternate for exponentation operation in python.
  `power(x, y)`

#### IMPORTANT NOTE
- Python allows usage of underscores to make large numeric literals easier to read 
	  `1_000_000_000` is a valid representation of `1000000000`
- Python supports scientific notation for floating-point values.
	  `xey` for example `1e3` means $x \times 10^y$ 

---
#### SUMMARY


---
#### FOOTNOTES

[^1]: Floor Operation
	The floor is the greatest integer less than or equal to the floating-point number
	Example:
	- Floor of 3.5 is 3 (Since 3 is the greatest integer less than or equal)
	- Floor of -3.5 is -4 (Since -4 is the greatest integer less than or equal to -3.5)
