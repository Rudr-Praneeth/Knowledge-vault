# Programming Fundamentals
TAGS: #DSA 
BUILT-ON: - 
ENABLES: - 
PREREQUSITIES: - 

---
## Input & Output
Input and Output (I/O) are fundamental concepts in programming.
- Input allows a program to receive data from the user, files, or other sources.
- Output allows it to display results.
- I/O is essential for creating interactive programs and performing tasks with dynamic data.

## Conditional Statements
Conditional statements help a program make decisions. They check whether a condition is true or false and execute different blocks of code based on the result. This allows programs to behave differently in different situations.
```py
						 CONDITIONAL STATEMENTS
// IF-ELSE STATEMENTS
if CONDITION:
	CODE_BLOCK
elif CONDITION:
	CODE_BLOCK
else: 
	CODE_BLOCK

// MATCH-CASE STATEMENTS
MATCH VARIABLE:
	CASE VALUE_1:
		CODE_BLOCK
	CASE VALUE_2:
		CODE_BLOCK
	CASE _:
		DEFAULT/NO_MATCH BLOCK 
		
// TERNARY EXPRESSION STATEMENTS
SUCCESS_CODE_BLOCK if CONDITION ELSE FAIL_CODE_BLOCK
```

## Loops
#### For-Loops
Allows to repeat a block of code a specific number of times.
In Python, a for loop is slightly different. It loops directly over an iterable and has two main parts: variable and iterable.
- ****Variable**** holds the current element from the iterable during each iteration.
- ****Iterable**** the collection of elements the loop goes through.
```py
for VARIABLE in range(START, END, STEP/STRIDE):
	CODE_BLOCK

for ITEM in ITERATABLE:
	CODE_BLOCK

for VARIABLE in range(START, END, STEP):
	for VARIABLE in range(START, END, STEP):
		CODE_BLOCK
```

#### While Loops
A while loop is a control structure that repeatedly executes a block of code as long as a specified condition remains true.
- The condition is checked before each iteration, and the loop stops once the condition becomes false.
- It is useful when the number of iterations is not known beforehand.
```py
while CONDITION:
	CODE_BLOCK
```

## Functions
A function is a block of code that performs a specific task and can be reused whenever needed.
- Makes programs simple and easy to understand by breaking into smaller parts.
- Accepts input (parameters) and gives output.
- Finding and fixing errors become easier.
#### Built-In Functions
These predefined functions provided by programming languages or libraries to perform common tasks such as mathematical calculations, input/output, or string operations.

#### User-defined Functions
These functions are functions written by programmers to perform specific tasks required in a program. They help organize code and allow reuse of logic whenever needed.
```py
def FUNCTION_NAME(PARAM1, PARAM2):
	CODE_BLOCK
	return RESULT

// CALLING FUNCTION
FUNCTION_NAME(ARG1, ARG2)
```

## Classes & Objects
In Data Structures, programs often work with complex data and operations that need to be organized efficiently. Object-Oriented Programming concepts like classes and objects help structure data and related operations in a clear and manageable way.
- Combines data (variables) and operations (functions) within a single structure.
- Helps manage complex implementations by keeping related functionality together.
- Improves reusability and organization when implementing data structures.
#### Class
A class is a blueprint or template used to create objects. It defines the structure that specifies the data members (attributes) and functions (methods) an object will contain. A class typically contains two main components:
***1. Attributes (Data Members)***: Attributes are the properties or characteristics of an object. They store information related to the object.
**2. Methods (Functions)***: Methods define the actions or behaviors that an object can perform.
**Features of a Class***
- Describes the data and operations related to a particular entity.
- Serves as a reusable template from which multiple objects can be created.
- Helps organize code by grouping related variables and functions.
- Supports modular programming, making programs easier to understand and maintain.

#### Object
An object is an instance of a class. It represents a real-world entity created using the class blueprint
- Stores actual values for class attributes.
- Allows you to call methods defined in the class.
- Multiple objects can exist from the same class, each holding different data.

