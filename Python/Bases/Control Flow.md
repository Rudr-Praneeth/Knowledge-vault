x`z# Control Flow
TAGS: #Python 
BUILT-ON: [[Python Fundamentals]]
ENABLES: - 
PREREQUSITIES: - 

---
# Control Flow
Control flow is the order in which a program's statements are executed. There are multiple ways of controlling the flow of a program. Some of these ways are as follows:
 - Conditional Statements
 - Loops

## Conditional Statements
#### Conditional Statements
Conditional Statements allow the control of flow of a program to depend on a condition. 
A condition determines which block executes at that decision point. A condition is made up of a Boolean value, a Boolean expression or multiple Boolean expressions combined using combining conditions: `and`, `or`, `not`. 
>Python permits mathematical-looking comparisons `Start <= Variable <= End`
```python
if CONDITION:
	CONDITIONAL_WORK()
elif CONDITION:
	CONDITIONAL_WORK()
else:
	FALLBACK_WORK()
```
Python evaluates a conditional chain from top to bottom and executes at most one branch in that chain i.e. python executes the first successful branch. Else block acts as an optional fallback block of code when no preceding chain executes.
Use an `if-elif` chain when you want to select one alternative from several. 
For independent `if` statements python evaluates **every** condition regardless of what happened before and is used when several actions may need to happen.

~={purple}***Truthiness in Conditions***=~:
Python does not require every `if` condition to literally evaluate to `True` or `False`. It tests the truthiness of the result.

~={purple}***Operator Precedence***=~:
- Comparison Operators
- Logical Not `not`
- Logical And `and`
- Logical Or `or`

~={purple}***Operand-Returning Behaviour***=~:
`and` and `or` do not necessarily return a Boolean. They return one of their operands. 
```python 
0 or 42 # 42 
"hello" or "bye" # "hello" 
7 and 9 # 9 
0 and 9 # 0 
```
- `or` returns the first truthy operand, else the last operand. 
- `and` returns the first falsy operand, else the last operand. 
- Inside an `if`, Python tests the truthiness of the resulting value.

#### Nested Conditions
A nested conditional is a conditional inside the body of another conditional. It represents a hierarchical decision: one decision determines whether another is relevant.

~={purple}***Guard Conditions***=~: 
A guard checks a prerequisite first and rejects early, keeping the main path at the same indentation level.

#### Match Statement
Provides a structured way to choose an action based on the value or structure of data, particularly useful when multiple alternatives need to be handled clearly.
Python executes the body of the first matching case.
- Each `case` defines a pattern to try matching against that value.
- `case _` is the wildcard fallback: it matches any value that reaches it.
- Single case can match several alternatives using `|` (OR pattern).
```python
match VARIABLE:
	#ANY OF THE STATES 1-3 MACTHED BY CASE 1
	case STATE_1 | STATE_2 | STATE_3:   
		BLOCK
	case STATE_4:
		BLOCK
	case STATE_5:
		BLOCK
	...
	case _:
		BLOCK
```
>NOTE
>`case variable_name`: captures the matched value and binds it to the name, whether or not that name existed before. It doesn't raise a `NameError` if the variable is not declared before the case statement and doesn't equate the value of the case variable to match variable it simply binds the case variable to the match variable object. `case variable_name` is a ***capture pattern***.
>`case _` is the wildcard fallback: it matches any value that reaches it without binding the value to a variable.

~={purple}***Types of Patterns***=~:
- ***Literal Patterns***: A pattern which matches a specific literal value
- ***Wildcard Pattern***: `case _` matches anything without binding the matched value to a variable. Commonly used as the fallback case.
- ***Alternative Patterns***: Use `|` to match any one of multiple patterns within a single case.
- ***Capture Pattern***: A case which is of the form case variable_name is known as a capture pattern as it matches with anything and stores the value in the variable variable_name.

##### Capture Pattern
A case which is of the form `case variable_name` is known as a ***capture pattern*** as it matches with anything and stores the value in the variable `variable_name`.
```python
match match_variable:
	case Literal:                              #REGULAR DATA CASE
		#BLOCK
	case case_variable:                        
		#BINDS CASE_VARIABLE NAME TO MATCH_VARIABLE OBJECT
		print(case_variable)                  #PRINTS MATCH_VARIABLE OBJECT
```

~={purple}***Sequence Patterns***=~:
A pattern which matches the structure and elements of a sequence, such as a list or tuple.
```python
match point:
    case (0, 0):              #MATCHES ORIGIN
        print("Origin")
    case (0, y):              #MATCHES (0, ANY_VALUE)
        print(y)
    case (x, y):              #MATCHES ANY TWO-ELEMENT SEQUENCE
        print(x, y)
```

~={purple}***Starred Sequence Patterns***=~:
Use `*variable` to capture the remaining elements of a sequence into a list. The captured list can be empty.
```python
match values:
    case [first, *middle, last]:
        #FIRST = FIRST ELEMENT
        #MIDDLE = LIST OF REMAINING ELEMENTS
        #LAST = LAST ELEMENT
        print(first, middle, last)
```

~={purple}***Mapping Patterns***=~:
A pattern which matches specified keys and their corresponding values in a dictionary. Mapping patterns normally allow additional keys. Use `**variable` to capture the remaining key-value pairs into a dictionary.
```python
response = {"status": 200, "message": "OK", "cached": True}
match response: 
    case {"status": 200, "message": message}: 
	    #MATCHES THE RESPONSE OBJECT SINCE 
	    # RESPONSE.status MATCHES CASE.status 
	    # BINDS CASE.message TO RESPONSE.message
	    # IGNORES RESPONSE.cached
        print("Success:", message)
    case {"status": 404}:
        print("Not found")
    case _:
        print("Other response")

match response:
    case {"status": status, **details}:
	    # BINDS STATUS = 200
	    # DETAILS: {message, cached}
        print(status, details)
```

~={purple}***Class Patterns***=~:
Python also supports patterns that match instances of classes and inspect selected attributes. The patterns check that `point` is an instance of the appropriate class and that its named attributes match the patterns.
```python
match point:
    case Point(x=0, y=0):
        print("Origin")
    case Point(x=x, y=y):
        print("Point:", x, y)
```

##### Guard Conditions
A guard is an additional Boolean condition attached to a `case` using `if`.
The pattern checks the shape or form of the subject. The guard checks an extra condition before allowing the case body to execute.
```python
match subject:
    case pattern if condition:
	    BLOCK
```
Guards are especially useful when a pattern captures data that needs further validation.
The `int() as value` pattern checks for an integer and captures it in `value`. 
```python
match score:
    case int() as value if value >= 90: 
	    # SCORE CHECKED IF int AND CAPTURED IN VALUE THEN COMPARED
        print("Excellent")
    case int() as value if value >= 70:
        print("Good")
    case int():
        print("Needs improvement")
    case _:
        print("Invalid score type")
        
# ANOTHER EXAMPLE
command = ("retry", 3)

match command:
    case ("retry", attempts) if attempts > 0:
        print(f"Retrying; attempts left: {attempts}")
    case ("retry", _):
        print("No retries remain")
    case _:
        print("Unsupported command")
```
A guard can use Boolean operators:
```python
match request:
    case {"user": user, "role": role} if user and role == "admin":
        print("Admin request")
    case _:
        print("Other request")
```

#### DESIGNING READABLE CODE 

| Situation                                        | Usually a good choice                           |
| ------------------------------------------------ | ----------------------------------------------- |
| A simple yes/no decision                         | `if` / `else`                                   |
| Several ordered conditions or ranges             | `if` / `elif` / `else`                          |
| A few distinct literal values                    | `match` or `if`/`elif`                          |
| Different structured input shapes                | `match` with structural patterns                |
| A recognized pattern needing extra validation    | A guarded `case`                                |
| A condition that should stop invalid input early | A guard clause using `if` and possibly `return` |

## Loops
A loop repeats a block of code until either the values provided by an iterable exhaust or a condition turns invalid.
Sometimes the user decides when to finish by entering a special value called a sentinel.
#### For Loop
A ``for loop`` repeats a block of code until the values produced by an iterable are exhausted.
~={purple}***General form of for loop***=~: 
```py
for VARIABLE in ITERABLE:
	REPEATING_WORK()
```
- ***Iterable***: an object that can provide a sequence of values, one at a time.
- ***Variable***: a name that is reassigned the current value after each iteration.
- ***Iteration***: a pass through a loop body is known as an iteration.

#### While Loop
A ``while loop`` repeats a block of code until a condition is falsified/turns invalid.
~={purple}***General form of while loop***=~: 
```py
LOOP_VARAIBLE = VALUE

while LOOP_CONDITION:
	REPEATABLE_CODEBLOCK()
	LOOP_VARIABLE_UPDATION()
	
LOOP_CONDITION: CONDITION 
```
~={purple}***Infinite While Loop Reasons***=~: 
A while loop may run infinitely due to following reasons:
- **Missing or wrong update:** the loop variable is never changed, or the wrong variable is changed.
- **Condition is always true:** `while True` with no reachable `break`.
- **`continue` skips the update:** the increment is placed after a `continue`.
- **`break` or exit path never reached:** the exit logic sits in a branch that never runs.
- **Non-converging algorithm:** e.g., an iterative method (Newton’s, binary search with bad midpoint math) that never meets its tolerance, or Collatz-style logic with a bug.
- **Logic error in the condition:** `and` vs `or`, or operator precedence errors.
- **Unhandled exceptions swallowed:** a `try/except` inside the loop catches the error and retries forever.

#### Loop Control Statements
A `break` statement immediately terminates the innermost enclosing loop. Execution continues with the first statement after that loop.
A `continue` statement skips the remainder of the current iteration and proceeds to the next iteration of the innermost enclosing loop.
A `pass` statement does nothing when executed. It is a placeholder statement that allows a syntactically required block to remain empty.

#### Else on Loops
A loop's `else` runs when the loop finishes normally without encountering `break`.
`continue` skips only one iteration. The loop continues and eventually finishes normally, so `else` still executes.













# END
---
#### SUMMARY


---
#### FOOTNOTES

