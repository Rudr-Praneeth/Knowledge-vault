# Phase I — The Core: Become Dangerous With Python
## Module 0 — Python Setup & Mental Model
**Goal:** Understand what Python actually is before writing serious code.
Chapters:
- [x] What Python is and where it fits
- [x] CPython, interpreters, bytecode, and execution
- [x] Installing and managing Python versions
- [x] REPL, scripts, modules, packages
- [x] `python`, `python3`, PATH, environments
- [x] Editors, IDEs, terminals, debugging
- [x] Running Python programs properly
- [x] Reading Python documentation
- [x] PEPs and the Python community
- [x] How to learn Python effectively

## Module 1 — Python Fundamentals
**Goal:** Become completely comfortable expressing ideas in Python.
Chapters:
- [x] Variables and names
- [x] Objects and references
- [x] Numbers
- [x] Strings
- [x] Booleans
- [x] `None`
- [x] Operators
- [x] Expressions vs statements
- [ ] Input/output
- [x] Type conversion
- [x] Comments and code structure
- [x] Basic error messages
- [x] Truthiness
- [x] Identity vs equality
- [x] Mutable vs immutable objects
**Mastery challenge:** Write small programs without looking up basic syntax.

## Module 2 — Control Flow
**Goal:** Control program behavior naturally.
Chapters:
- [x] `if / elif / else`
- [x] Nested conditions
- [x] `for`
- [x] `while`
- [x] `break`
- [x] `continue`
- [x] `pass`
- [x] `else` on loops
- [x] `match`
- [x] Pattern matching fundamentals
- [x] Guard conditions
- [x] Designing readable branching logic
**Mastery challenge:** Solve dozens of logic problems from scratch.

## Module 3 — Data Structures
**Goal:** Know Python's built-in data structures at an expert level.
Chapters:
- [x] Lists
- [x] Tuples
- [x] Dictionaries
- [ ] Sets
- [ ] Strings as sequences
- [ ] Indexing
- [ ] Slicing
- [ ] Iteration
- [ ] Nested structures
- [ ] Hashing
- [ ] Membership testing
- [ ] Copying
- [ ] Shallow vs deep copy
- [ ] Choosing the right data structure
- [ ] Time complexity of common operations
This module is **huge** because Python mastery depends heavily on data modeling.

## Module 4 — Functions
**Goal:** Think in reusable abstractions.
Chapters:
- [ ] Defining functions
- [ ] Parameters
- [ ] Return values
- [ ] Positional arguments
- [ ] Keyword arguments
- [ ] Default arguments
- [ ] `*args`
- [ ] `**kwargs`
- [ ] Positional-only parameters
- [ ] Keyword-only parameters
- [ ] Scope
- [ ] LEGB
- [ ] Closures
- [ ] Recursion
- [ ] First-class functions
- [ ] Higher-order functions
- [ ] Lambda
- [ ] Function annotations
- [ ] Docstrings
- [ ] Designing good APIs

---
# Phase II — Become a Real Python Programmer
## Module 5 — Comprehensions & Iteration
- [ ] List comprehensions
- [ ] Set comprehensions
- [ ] Dictionary comprehensions
- [ ] Generator expressions
- [ ] Iterables
- [ ] Iterators
- [ ] `iter()`
- [ ] `next()`
- [ ] `StopIteration`
- [ ] Lazy evaluation
- [ ] `yield`
- [ ] Generator functions
- [ ] Generator pipelines
- [ ] Memory-efficient iteration

## Module 6 — Exceptions & Defensive Programming
- [ ] Exceptions
- [ ] `try`
- [ ] `except`
- [ ] `else`
- [ ] `finally`
- [ ] Raising exceptions
- [ ] Custom exceptions
- [ ] Exception chaining
- [ ] Exception hierarchy
- [ ] EAFP vs LBYL
- [ ] Designing failure behavior
- [ ] Logging errors
- [ ] Debugging exceptions
- [ ] Writing resilient programs

## Module 7 — Modules, Packages & Imports
1. Modules
2. Import mechanics
3. `import`
4. `from ... import`
5. Aliasing
6. `__name__`
7. `__main__`
8. Package structure
9. `__init__.py`
10. Absolute vs relative imports
11. Import search path
12. Circular imports
13. Import caching
14. `sys.path`
15. Packaging fundamentals

## Module 8 — Object-Oriented Python
**Goal:** Become extremely strong at Python's object model.
Chapters:
1. Classes and objects
2. Instance attributes
3. Class attributes
4. Methods
5. Constructors
6. Encapsulation
7. Properties
8. Class methods
9. Static methods
10. Inheritance
11. Method overriding
12. `super()`
13. Multiple inheritance
14. MRO
15. Composition vs inheritance
16. Abstract base classes
17. Protocol-oriented design
18. Dataclasses
19. `__slots__`
20. Object lifecycle

---
# Phase III — Python's Secret Weapons
## Module 9 — The Python Data Model
This is where things get serious.
Chapters:
1. The object model
2. `__repr__`
3. `__str__`
4. `__len__`
5. `__bool__`
6. `__eq__`
7. Ordering methods
8. Hashability
9. `__getitem__`
10. `__setitem__`
11. `__iter__`
12. `__next__`
13. `__contains__`
14. Callable objects
15. Arithmetic dunder methods
16. Context manager protocol
17. Attribute access
18. Descriptors
19. Method binding
20. Protocols

## Module 10 — Decorators
1. Functions as objects
2. Closures revisited
3. Decorator mechanics
4. Function decorators
5. Decorator factories
6. `functools.wraps`
7. Class decorators
8. Stateful decorators
9. Stacking decorators
10. Real-world decorator patterns

## Module 11 — Context Managers
1. `with`
2. Context manager protocol
3. `__enter__`
4. `__exit__`
5. `contextlib`
6. Custom context managers
7. Resource management
8. Exception handling inside contexts
9. Nested contexts
10. Practical patterns

## Module 12 — Advanced Functions & Functional Python
1. `map`
2. `filter`
3. `reduce`
4. `functools`
5. `partial`
6. `lru_cache`
7. `singledispatch`
8. Callables
9. Function composition
10. Functional design patterns

---
# Phase IV — Write Production-Grade Python
## Module 13 — Files, Paths & Serialization
1. File handling
2. Text vs binary
3. Encoding
4. `pathlib`
5. Directory traversal
6. Temporary files
7. CSV
8. JSON
9. Pickle
10. Serialization design
11. Streaming files
12. Resource safety


## Module 14 — Standard Library Mastery
We won't memorize the whole standard library.
We'll learn the **high-value weapons**:
- `collections`
- `itertools`
- `functools`
- `operator`
- `math`
- `statistics`
- `datetime`
- `zoneinfo`
- `decimal`
- `fractions`
- `random`
- `re`
- `json`
- `csv`
- `pathlib`
- `os`
- `sys`
- `subprocess`
- `shutil`
- `tempfile`
- `logging`
- `argparse`
- `enum`
- `dataclasses`
- `contextlib`
- `typing`
- `inspect`
- `importlib`

## Module 15 — Testing
**Goal:** Stop hoping your code works.
Chapters:
1. Why testing matters
2. Unit testing
3. `unittest`
4. `pytest`
5. Assertions
6. Fixtures
7. Parametrization
8. Mocking
9. Patching
10. Integration testing
11. Test organization
12. Property-based testing
13. Test-driven development
14. Testing failure cases
15. Testing asynchronous code

## Module 16 — Debugging & Observability
1. Reading tracebacks
2. Debugging systematically
3. `pdb`
4. IDE debuggers
5. Logging
6. Log levels
7. Structured logging concepts
8. Assertions
9. Profiling
10. Tracing
11. Diagnosing memory problems
12. Diagnosing performance problems
13. Production debugging

---
# Phase V — Type Systems & Code Quality
## Module 17 — Type Hints
1. Why types?
2. Built-in generic types
3. `list[str]`
4. `dict[str, int]`
5. `Optional`
6. Unions
7. Type aliases
8. `Literal`
9. `TypeVar`
10. Generic types
11. Protocols
12. `TypedDict`
13. `Callable`
14. `Self`
15. Static type checkers
16. Designing typed APIs

## Module 18 — Professional Python Style
1. PEP 8
2. Naming
3. Formatting
4. Imports
5. Documentation
6. API design
7. Readability
8. Complexity
9. Refactoring
10. Code smells
11. Maintainability
12. Clean architecture concepts

---
# Phase VI — Concurrency, Parallelism & Performance
## Module 19 — Concurrency Fundamentals
1. Processes vs threads
2. Concurrency vs parallelism
3. Race conditions
4. Shared state
5. Locks
6. Queues
7. Synchronization
8. Threading
9. Thread pools

## Module 20 — `asyncio`
1. Event loops
2. Coroutines
3. `async`
4. `await`
5. Tasks
6. Futures
7. Cancellation
8. Timeouts
9. Async context managers
10. Async iterators
11. Concurrent task patterns
12. Debugging async code

## Module 21 — Multiprocessing
1. Processes
2. Process pools
3. IPC
4. Queues
5. Pipes
6. Shared memory
7. Serialization costs
8. Multiprocessing design
9. When multiprocessing makes sense

## Module 22 — Performance Engineering
1. Big-O
2. Benchmarking
3. `timeit`
4. Profiling
5. CPU-bound work
6. I/O-bound work
7. Memory usage
8. Algorithmic optimization
9. Data structure optimization
10. Caching
11. Vectorization concepts
12. Python performance traps

---
# Phase VII — Internet, Systems & Real Software
## Module 23 — Networking
1. HTTP fundamentals
2. URLs
3. Requests/responses
4. REST APIs
5. JSON APIs
6. Authentication
7. Sessions
8. Cookies
9. HTTP clients
10. Async networking
11. WebSockets
12. Retries and timeouts
13. Rate limiting

## Module 24 — Databases
1. SQL fundamentals
2. SQLite
3. PostgreSQL concepts
4. Python database APIs
5. Transactions
6. Connection pooling
7. ORMs
8. SQLAlchemy
9. Query optimization
10. Database design

## Module 25 — CLI & Automation
1. Command-line applications
2. `argparse`
3. Environment variables
4. Configuration
5. Automation scripts
6. Shell interaction
7. Subprocesses
8. Scheduling
9. Cross-platform automation
10. Building real CLI tools

---
# Phase VIII — Web Development
## Module 26 — Web Fundamentals
1. How the web works
2. HTTP deeply
3. HTML
4. CSS concepts
5. Browser/server architecture
6. APIs
7. Sessions
8. Authentication
9. Cookies
10. CORS
11. Security fundamentals

## Module 27 — Python Web Development
We'll build with modern frameworks rather than treating web development as theory.
Topics:
1. WSGI
2. ASGI
3. FastAPI
4. Flask
5. Django
6. Routing
7. Middleware
8. Validation
9. Dependency injection
10. Authentication
11. Background tasks
12. WebSockets
13. Deployment

---
# Phase IX — Expert-Level Python
## Module 28 — Metaprogramming
1. Dynamic attributes
2. `getattr`
3. `setattr`
4. `hasattr`
5. `__getattr__`
6. `__getattribute__`
7. `__setattr__`
8. Dynamic class creation
9. `type`
10. Metaclasses
11. When metaclasses are useful
12. When metaclasses are a terrible idea

## Module 29 — Descriptors
1. Descriptor protocol
2. Data descriptors
3. Non-data descriptors
4. Attribute lookup
5. Method descriptors
6. `property`
7. Custom descriptors
8. Framework-style patterns

## Module 30 — Introspection
1. `dir`
2. `type`
3. `id`
4. `vars`
5. `inspect`
6. Signatures
7. Frames
8. Code objects
9. Function internals
10. Runtime introspection

## Module 31 — Python Internals
This is where we stop being merely “Python programmers.”
1. CPython architecture
2. Source → AST → bytecode
3. Compilation
4. Bytecode
5. Interpreter execution
6. Stack frames
7. Function objects
8. Code objects
9. Reference counting
10. Garbage collection
11. Memory allocation
12. Interning
13. C extensions
14. The GIL and its evolution
15. Interpreter implementations
16. Why Python behaves the way it does

---
# Phase X — Advanced Ecosystem
## Module 32 — Packaging & Distribution
1. `pyproject.toml`
2. Build systems
3. Package metadata
4. Wheels
5. Source distributions
6. Dependency management
7. Versioning
8. Publishing packages
9. Private packages
10. Reproducible environments

## Module 33 — Virtual Environments & Dependency Management
1. `venv`
2. Dependency pinning
3. Lock files
4. Dependency conflicts
5. Environment isolation
6. Development vs production dependencies
7. Modern Python project workflows

## Module 34 — Security
1. Input validation
2. Injection
3. Unsafe deserialization
4. Secrets management
5. Authentication
6. Authorization
7. Dependency vulnerabilities
8. Cryptography basics
9. Secure coding practices
10. Threat modeling

---
# Phase XI — Specialized Python
After you've mastered the core, we can branch.
## Module 35 — Data Science
- NumPy
- pandas
- visualization
- scientific computing
- numerical performance

## Module 36 — Machine Learning
- scikit-learn
- PyTorch
- model pipelines
- experimentation
- serving

## Module 37 — Automation & DevOps
- system administration
- infrastructure automation
- CI/CD
- cloud SDKs
- monitoring

## Module 38 — Backend Engineering
- scalable APIs
- async systems
- queues
- caching
- distributed systems

## Module 39 — Data Engineering
- ETL/ELT
- pipelines
- streaming
- orchestration
- warehouses

## Module 40 — Security Engineering
- scripting
- networking
- protocol analysis
- automation
- defensive tooling

---
# Phase XII — The Beast Tier
This is the part most tutorials completely miss.

## Module 41 — Algorithms & Data Structures
You'll implement things yourself:
- arrays
- linked lists
- stacks
- queues
- hash tables
- trees
- heaps
- graphs
- tries
- union-find
- sorting
- searching
- dynamic programming
- greedy algorithms
- graph algorithms
And you'll implement many of them **without relying on Python's built-ins first**.

## Module 42 — Software Architecture
1. SOLID
2. Cohesion
3. Coupling
4. Dependency inversion
5. Layered architecture
6. Hexagonal architecture
7. Event-driven architecture
8. Domain-driven design concepts
9. Distributed systems concepts
10. Designing large Python systems

## Module 43 — Open Source Code Mastery
We'll learn to enter unfamiliar repositories and understand them.
1. Reading repository structure
2. Following execution paths
3. Finding entry points
4. Reading tests first
5. Understanding dependencies
6. Git archaeology
7. Debugging existing systems
8. Making changes safely
9. Code review
10. Contributing to open source

## Module 44 — Build Your Own Python Tools
Projects like:
1. CLI application
2. Web scraper
3. REST API
4. Async service
5. Database application
6. Task queue
7. Package published to PyPI
8. Testing framework component
9. Mini ORM
10. Mini web framework
11. Dependency injection framework
12. Python linter
13. Bytecode/AST analyzer
14. Tiny programming language/interpreter

---
# Phase XIII — Final Boss
## Module 45 — Build a Serious Production System
You'll build one substantial system from zero.
It should include:
- architecture
- typed Python
- database
- API
- authentication
- async processing
- tests
- logging
- monitoring
- packaging
- CI/CD
- documentation
- performance profiling
- security review
- deployment
