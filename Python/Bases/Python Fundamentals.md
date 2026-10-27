# Python Fundamentals
TAGS: #Python 
BUILT-ON: [[Python Introduction]]
ENABLES: - 
PREREQUSITIES: [[Python Fundamentals]] [[Python Hacks & Essentials]]

---
## Variables, Objects & Reference
#### Variables
A variable is a named place in memory that is used to reference an object. 
In Python, the assignment operation binds a name to an object where a name helps communicate what the object represent i.e. allows to give a meaningful label to an value.
#### Object
An object is a runtime entity that python creates and uses. An object comprises of an Identity, a type and a value/state.
An Identity is a unique differentiator that is used to distinguish one object from another during its lifetime. An object's identity is accessible by:
```py
id(VARIABLE)
```
`is` operator in python is used to check the identity of the objects. `VARIABLE_1 is VARIABLE_2` tells us whether both the variables `VARIABLE_1` and `VARIABLE_2` reference the same object.
#### Reference
A reference describes the relationship between a name and an object. With the use of aliasing multiple names can reference the same object in memory. 
When Python evaluates `y = x`, it evaluates `x` to the object it currently refers to, then binds `y` to that same object. It does not inherently create a new object.
>~={purple}KEY CONCEPT=~:
>***Mutation changes the object's value/state*** which is reflected in all the names that referencing that object. Whereas ***Rebinding/Reassignment changes the object the name refers to***.

## Python Datatypes
Python supports multiple types of values/data i.e. Literals[^1]. All the data in python are a runtime entity known as an Object.
The datatypes supported in Python are [[Python Datatypes]]

## Python Operators
An operator is syntax that tells Python to perform an operation on one or more objects. 
#### Arithmetic Operators 
- Addition: `OPERAND + OPERAND` 
- Subtraction: `OPERAND - OPERAND`
- Multiplication: `OPERAND * OPERAND`
- Division: `OPERAND / OPERAND`
- Floor Division: `OPERAND // OPERAND`
- Modulo: `OPERAND % OPERAND`
- Exponentiation: `OPERAND ** OPERAND`
#### Comparison Operators
Operators comparing values and returning Booleans
- Equals: `OPERAND/EXPRESSION == OPERAND/EXPRESSION`
- Not Equals: `OPERAND/EXPRESSION != OPERAND/EXPRESSION`
- Lesser Than: `OPERAND/EXPRESSION < OPERAND/EXPRESSION`
- Greater  Than: `OPERAND/EXPRESSION > OPERAND/EXPRESSION`
- Lesser than or Equals: `OPERAND/EXPRESSION <= OPERAND/EXPRESSION`
- Greater than or Equals: `OPERAND/EXPRESSION >= OPERAND/EXPRESSION`
#### Logical Operators
Operators combing/reversing logical conditions
- Logical and: `OPERAND/EXPRESSION and OPERAND/EXPRESSION` 
- Logical or: `OPERAND/EXPRESSION or OPERAND/EXPRESSION`
- Logical not: `not OPERAND/EXPRESSION`
#### Assignment Operators
Assignment binds a name to an object. Augmented assignment combines an operation with assignment.
- `OPERAND/OBJECT += OPERAND`
- `OPERAND/OBJECT -= OPERAND`
- `OPERAND/OBJECT *= OPERAND`
- `OPERAND/OBJECT /= OPERAND`
- `OPERAND/OBJECT //= OPERAND`
- `OPERAND/OBJECT %= OPERAND`
- `OPERAND/OBJECT **= OPERAND`
The equivalence above is a useful mental model, but it isn't exact for every object. Mutable objects can behave differently under augmented assignment because an operation may modify an object in place.
For example, `+=` on an integer produces a new integer result and rebinds the name. On a list, it can modify the existing list. That distinction connects directly to what you learned about objects, references, mutation, and rebinding.
#### Membership Operators
Membership asks whether an item belongs to a container or sequence.
- `in` or `not in`
#### Identity Operators
Identity asks whether two references point to the same object.
- `is` or `is not`

## Expressions and Statements
An expression is a piece of code that Python evaluates to produce a value. Expressions let you describe computations and obtain values that can be used elsewhere.

A statement is a complete instruction that Python executes. These instruct Python to do something: bind a name, call a function, or import a module.
A function call is an expression because it has a return value. When written alone on a line, it is used as an expression statement: Python evaluates the call and discards its return value.

## Input/Output
Input/output (I/O) is the process through which a program receives information from outside and communicates results to the outside world.
- Input: information entering a program.
- Output: information leaving a program.
[[Input-Output in Python]]

## Type Conversions
Type conversion means converting a value from one data type to another.
#### Explicit conversion
Conversion of type using explicit commands also called type casting.
#### Implicit conversion
Python automatically converts certain values during an operation when supported.

## Truthiness and Falsiness
Truthiness and Falsiness describe how Python evaluates an object in a Boolean context, i.e. whether an object behaves like `True` or `False` when a condition is evaluated.
In Python, `bool(OBJECT)` converts an object into its corresponding Boolean value, either `True` or `False`.
- **Truthy:** An object is truthy if its Boolean evaluation is `True`.
- **Falsy:** An object is falsy if its Boolean evaluation is `False`.
Common falsy values include:
- `False` — the Boolean false value.
- `None` — represents the absence of a value.
- Numeric zero: `0`, `0.0`, `0j`.
- Empty sequences: `""`, `[]`, `()`.
- Empty collections: `{}`, `set()`, `frozenset()`.
- Other instances of built-in types that define themselves as empty or false.
**Truthiness is a rule for evaluating objects in Boolean contexts, not a conversion of the original object into a Boolean.** Empty values and numeric zero are generally falsy; non-empty strings and collections, and non-zero numbers, are truthy. Custom objects can define their own truthiness through `__bool__()` or `__len__()`.

## Identity vs Equality
- **Equality (**`**==**`**):** Checks whether two objects are equal according to their equality behavior.
- **Identity (**`**is**`**):** Checks whether two references point to the same object.

## Mutable vs Immutable Objects
Mutability is an object's ability to have its state/value changed after creation.
- **Mutable:** Objects can be modified in place. Examples: `list`, `dict`, `set`.
- **Immutable:** Objects cannot be modified in place. Examples: `int`, `float`, `bool`, `str`, `tuple`, `frozenset`, `NoneType`.

#### Mutation vs Rebinding
**Mutation** changes an existing object's state, making the change visible through all references to that object.
**Rebinding** changes the object a name refers to; it does not inherently modify the previously referenced object.
>Immutable objects cannot be modified in place. Operations on them return results that can be assigned to a name, rebinding it.

#### Aliasing and Copying
Aliasing occurs when multiple names reference the same object. Mutations through one alias are visible through the others.
Copying creates a separate object. The degree of independence depends on whether the copy is shallow or deep.
***Shallow Copy***:
A shallow copy creates a new outer object but retains references to nested objects.
***Deep Copy***:
A deep copy recursively copies nested objects, creating independent copies of the nested object structure.
```py
SHALLOW = ORIGINAL.copy()  
SHALLOW = copy.copy(ORIGINAL)

DEEP = copy.deepcopy(ORIGINAL)
```
***Key Distinction***
- **Shallow copy:** Creates a new outer object; nested mutable objects may be shared.
- **Deep copy:** Recursively copies nested objects, avoiding shared nested mutable objects in typical cases.

# END
---
#### SUMMARY


---
#### FOOTNOTES

[^1]: A literal is a fixed value/data written directly in Python code.
