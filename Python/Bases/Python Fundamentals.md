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








































---
#### SUMMARY


---
#### FOOTNOTES

[^1]: A literal is a fixed value/data written directly in Python code.
