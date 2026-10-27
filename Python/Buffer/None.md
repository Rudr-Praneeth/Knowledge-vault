# None
TAGS: #Python 
BUILT-ON: [[Python Datatypes]]
ENABLES: - 
PREREQUSITIES:  -

---
## None
**`None`** is a special Python object representing the absence of a value or the lack of a meaningful result.
- The type is `NoneType`.
- `None` is a **singleton**: only one `None` object exists, and the literal `None` always refers to it.
- It is a keyword and is case-sensitive.

#### Common Uses
- A value that is not yet known, not available, or intentionally absent.
- The default return value of a function with no `return` statement.
- A placeholder default for optional parameters.

>~={purple}NOTE=~:
>All of these evaluate to `False` in a Boolean context, but they are different objects of different types.
>`None == False`, `None == 0` and `None == ""` are all `False`.
>`None == None` is `True`.

#### Checking for None
- **`<VALUE> is None`**:`True` if `<VALUE>` is the `None` object.
- **`<VALUE> is not None`**: `True` if `<VALUE>` is anything other than `None`.
- `is` checks identity: whether two names refer to the same object. Since `None` is a singleton, `is None` is the idiomatic check.

#### None vs an Undefined Name
- A name bound to `None` exists and has a value: the `None` object.
- A name that has never been defined cannot be resolved and raises `NameError`.

---
## Three-State Logic with Booleans
`None` lets a variable distinguish a definite answer from missing information.
- `True`: explicitly enabled.
- `False`: explicitly disabled.
- `None`: not configured or unknown.

# END
---
#### FOOTNOTES


