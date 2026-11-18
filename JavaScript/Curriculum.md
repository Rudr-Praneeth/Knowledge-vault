# JavaScript Mastery Curriculum
**Scope:** JavaScript language, browser JavaScript, Web APIs, Node.js, Express.js, backend engineering, runtime internals, and professional software engineering.
**Hierarchy:** Phase → Module → Chapter. Each numbered topic below is a chapter-level learning objective. Use the checkboxes to track completion.

---
## Curriculum objectives
Develop three complementary competencies:
1. **Language mastery:** Understand JavaScript syntax, semantics, execution, data types, functions, objects, and advanced language features.
2. **Runtime mastery:** Understand JavaScript engines, browser and Node.js runtimes, the event loop, memory management, concurrency, and performance.
3. **Development mastery:** Build robust, secure, maintainable browser applications and backend systems with JavaScript, Node.js, and Express.js.

### Standard chapter learning cycle
For each chapter:
1. [ ] **Conceptual learning:** Define the concept, explain why it exists, and identify its role in the language or runtime.
2. [ ] **Internal mechanics:** Explain how it works, including relevant execution, memory, runtime, or specification behavior.
3. [ ] **Code implementation:** Write examples independently, explore edge cases, and solve practical exercises.
4. [ ] **Knowledge assessment:** Answer conceptual questions, trace code, predict outputs, diagnose bugs, and justify design choices.
5. [ ] **Practical mastery:** Complete an implementation that demonstrates independent application.

### Mastery levels
Level Standard
L1 --- Recognition Recognize and correctly identify the concept.
L2 --- Explanation Explain what it does, how it works, and why it behaves that way.
L3 --- Implementation Use or implement it independently.
L4 --- Debugging Diagnose edge cases, failures, and incorrect behavior.
L5 --- Engineering Apply it appropriately in maintainable, performant, secure systems.
**Target:** Reach L5 for critical subjects such as closures, prototypes, execution contexts, promises, event loops, memory management, streams, middleware, security, and application architecture. For rare or specialized features, understand the semantics and appropriate use cases without forcing them into everyday projects.

---
# PHASE 1 - JavaScript Language Foundations
**Objective:** Understand the language, its syntax, semantics, fundamental data model, and execution behavior.
## Module 1. Introduction to JavaScript
- [x] 1.1 Definition of JavaScript
- [x] 1.2 Characteristics of JavaScript
- [x] 1.3 JavaScript vs. ECMAScript
- [x] 1.4 JavaScript environments: browser and server
- [ ] 1.5 JavaScript engines and runtimes
- [ ] 1.6 Working and execution of JavaScript
- [ ] 1.7 JavaScript execution model
- [ ] 1.8 JavaScript development tools and environment setup
**Prior progress:** The introductory topics---definition, characteristics, working/execution, and execution model---were previously studied. Revisit them briefly and assess retention before marking complete.

## Module 2. JavaScript Syntax and Programming Fundamentals
- [ ] 2.1 JavaScript syntax and grammar
- [ ] 2.2 Statements and expressions
- [ ] 2.3 Identifiers and reserved keywords
- [ ] 2.4 Comments and code structure
- [ ] 2.5 Semicolons and Automatic Semicolon Insertion (ASI)
- [ ] 2.6 Strict mode (`"use strict"`)
- [ ] 2.7 Variables and declarations: `var`, `let`, `const`
- [ ] 2.8 Variable initialization and reassignment
- [ ] 2.9 Scope: global, function, and block scope
- [ ] 2.10 Hoisting and the Temporal Dead Zone (TDZ)
- [ ] 2.11 Variable shadowing
- [ ] 2.12 Naming conventions and code readability

## Module 3. Data Types and Type System
- [ ] 3.1 Understanding the JavaScript type system
- [ ] 3.2 Primitive and non-primitive values
- [ ] 3.3 Number and IEEE 754 representation
- [ ] 3.4 String
- [ ] 3.5 Boolean
- [ ] 3.6 Undefined
- [ ] 3.7 Null
- [ ] 3.8 Symbol
- [ ] 3.9 BigInt
- [ ] 3.10 Objects and functions as objects
- [ ] 3.11 Dynamic typing
- [ ] 3.12 Type coercion and conversion
- [ ] 3.13 Implicit vs. explicit conversion
- [ ] 3.14 Truthy and falsy values
- [ ] 3.15 `typeof` and its peculiarities
- [ ] 3.16 `null` vs. `undefined`
- [ ] 3.17 Primitive value behavior vs. object reference behavior

## Module 4. Operators and Expressions
- [ ] 4.1 Arithmetic operators
- [ ] 4.2 Assignment operators
- [ ] 4.3 Comparison operators
- [ ] 4.4 Equality: `==` vs. `===`
- [ ] 4.5 Logical operators
- [ ] 4.6 Short-circuit evaluation
- [ ] 4.7 Nullish coalescing (`??`)
- [ ] 4.8 Optional chaining (`?.`)
- [ ] 4.9 Unary operators
- [ ] 4.10 Bitwise operators
- [ ] 4.11 Conditional (ternary) operator
- [ ] 4.12 `in` and `instanceof`
- [ ] 4.13 `delete`, `void`, and `typeof`
- [ ] 4.14 Operator precedence and associativity
- [ ] 4.15 Expression evaluation order

## Module 5. Control Flow and Iteration
- [ ] 5.1 Conditional statements
- [ ] 5.2 `if`, `else if`, and `else`
- [ ] 5.3 `switch`
- [ ] 5.4 Loops and iteration fundamentals
- [ ] 5.5 `for`
- [ ] 5.6 `while` and `do...while`
- [ ] 5.7 `break` and `continue`
- [ ] 5.8 `for...in`
- [ ] 5.9 `for...of`
- [ ] 5.10 Labeled statements
- [ ] 5.11 Nested loops
- [ ] 5.12 Iteration performance and complexity considerations

## Module 6. Working with JavaScript Built-ins
- [ ] 6.1 Number and Math
- [ ] 6.2 String and template literals
- [ ] 6.3 Array fundamentals
- [ ] 6.4 Array methods
- [ ] 6.5 Array transformations: `map`, `filter`, and `reduce`
- [ ] 6.6 Array searching and sorting
- [ ] 6.7 Object fundamentals
- [ ] 6.8 Object utility methods
- [ ] 6.9 Date and time
- [ ] 6.10 Regular expressions
- [ ] 6.11 JSON serialization and parsing
- [ ] 6.12 Internationalization with `Intl`
**Phase 1 practical outcome:** Build small programs for calculations, data processing, validation, searching, sorting, and transformations without depending on external libraries.

---

# PHASE 2 - Functions, Scope, and JavaScript's Object Model
**Objective:** Understand the mechanisms that make JavaScript fundamentally different from many other programming languages.

## Module 7. Functions --- Deep Understanding
- [ ] 7.1 Function declarations
- [ ] 7.2 Function expressions
- [ ] 7.3 Anonymous and named functions
- [ ] 7.4 Arrow functions
- [ ] 7.5 Function parameters and arguments
- [ ] 7.6 Default parameters
- [ ] 7.7 Rest parameters
- [ ] 7.8 The `arguments` object
- [ ] 7.9 Return values
- [ ] 7.10 First-class functions
- [ ] 7.11 Higher-order functions
- [ ] 7.12 Callback functions
- [ ] 7.13 Pure and impure functions
- [ ] 7.14 Function composition
- [ ] 7.15 Immediately Invoked Function Expressions (IIFE)
- [ ] 7.16 Recursive functions
- [ ] 7.17 Function factories
- [ ] 7.18 Currying and partial application
- [ ] 7.19 Memoization
- [ ] 7.20 Function properties and methods

## Module 8. Execution Context and Call Stack --- Internals
- [ ] 8.1 What is an execution context?
- [ ] 8.2 Global execution context
- [ ] 8.3 Function execution context
- [ ] 8.4 Eval execution context
- [ ] 8.5 Creation phase and execution phase
- [ ] 8.6 Lexical environments
- [ ] 8.7 Environment records
- [ ] 8.8 Variable environment
- [ ] 8.9 Lexical environment relationships
- [ ] 8.10 Scope chain
- [ ] 8.11 Identifier resolution
- [ ] 8.12 Execution context stack
- [ ] 8.13 Call stack mechanics
- [ ] 8.14 Stack overflow
- [ ] 8.15 Execution context lifecycle
- [ ] 8.16 How closures interact with execution contexts

## Module 9. Scope, Closures, and Lexical Environment
- [ ] 9.1 Static (lexical) scoping
- [ ] 9.2 Global scope
- [ ] 9.3 Function scope
- [ ] 9.4 Block scope
- [ ] 9.5 Lexical scope
- [ ] 9.6 Scope chain resolution
- [ ] 9.7 Closure definition
- [ ] 9.8 How closures are created
- [ ] 9.9 Closure and lexical environment relationship
- [ ] 9.10 Data encapsulation using closures
- [ ] 9.11 Private state
- [ ] 9.12 Closures in callbacks
- [ ] 9.13 Closures in loops
- [ ] 9.14 Common closure pitfalls
- [ ] 9.15 Memory implications of closures
- [ ] 9.16 Practical closure patterns

## Module 10. The `this` Keyword and Function Invocation
- [ ] 10.1 Understanding `this`
- [ ] 10.2 Global execution and `this`
- [ ] 10.3 Default binding
- [ ] 10.4 Implicit binding
- [ ] 10.5 Explicit binding
- [ ] 10.6 `call()`
- [ ] 10.7 `apply()`
- [ ] 10.8 `bind()`
- [ ] 10.9 Constructor invocation
- [ ] 10.10 `this` inside arrow functions
- [ ] 10.11 Lexical `this`
- [ ] 10.12 `this` in event handlers
- [ ] 10.13 `this` in classes
- [ ] 10.14 Method extraction and lost context
- [ ] 10.15 Function borrowing

## Module 11. Objects and Property Mechanics
- [ ] 11.1 Object creation
- [ ] 11.2 Object literals
- [ ] 11.3 Constructor functions
- [ ] 11.4 Property keys and values
- [ ] 11.5 Property descriptors
- [ ] 11.6 Writable, enumerable, and configurable attributes
- [ ] 11.7 Own vs. inherited properties
- [ ] 11.8 Property access and lookup
- [ ] 11.9 Property enumeration
- [ ] 11.10 Property ownership
- [ ] 11.11 Getters and setters
- [ ] 11.12 Computed property names
- [ ] 11.13 Object destructuring
- [ ] 11.14 Spread and rest syntax
- [ ] 11.15 Shallow copying
- [ ] 11.16 Deep copying
- [ ] 11.17 Object immutability
- [ ] 11.18 `Object.freeze()`, `Object.seal()`, and `Object.preventExtensions()`

## Module 12. Prototypes and Inheritance
- [ ] 12.1 Understanding prototypes
- [ ] 12.2 The prototype property
- [ ] 12.3 `[[Prototype]]` internal mechanism
- [ ] 12.4 Prototype chain
- [ ] 12.5 Property lookup through prototypes
- [ ] 12.6 Prototype delegation
- [ ] 12.7 `Object.create()`
- [ ] 12.8 Constructor functions and prototypes
- [ ] 12.9 `new` operator mechanics
- [ ] 12.10 Prototype-based inheritance
- [ ] 12.11 Constructor inheritance
- [ ] 12.12 Method overriding
- [ ] 12.13 Shadowing inherited properties
- [ ] 12.14 `instanceof` internals
- [ ] 12.15 `Object.getPrototypeOf()`
- [ ] 12.16 `Object.setPrototypeOf()`
- [ ] 12.17 Prototype pollution
- [ ] 12.18 Composition vs. inheritance

## Module 13. Object-Oriented JavaScript
- [ ] 13.1 Object-oriented programming principles
- [ ] 13.2 Encapsulation
- [ ] 13.3 Abstraction
- [ ] 13.4 Inheritance
- [ ] 13.5 Polymorphism
- [ ] 13.6 ES6 classes
- [ ] 13.7 Class constructors
- [ ] 13.8 Instance methods
- [ ] 13.9 Static methods and properties
- [ ] 13.10 Class fields
- [ ] 13.11 Private fields (`#`)
- [ ] 13.12 Getters and setters in classes
- [ ] 13.13 `extends` and `super`
- [ ] 13.14 Inheritance internals
- [ ] 13.15 Method overriding
- [ ] 13.16 Composition patterns
- [ ] 13.17 Factory functions vs. classes
- [ ] 13.18 When to use OOP in JavaScript

**Phase 2 practical outcome:** Build reusable function libraries, custom data structures, object-oriented systems, and closure-based modules. Explain `this`, closures, prototypes, and inheritance without relying on memorized definitions.

---

# PHASE 3 --- Advanced JavaScript and Language Internals
**Objective:** Develop the deeper understanding needed to reason about JavaScript behavior, implement abstractions, and debug difficult problems.

## Module 14. Equality, Coercion, and Language Semantics
- [ ] 14.1 Strict equality
- [ ] 14.2 Abstract equality
- [ ] 14.3 SameValue comparison
- [ ] 14.4 SameValueZero
- [ ] 14.5 `Object.is()`
- [ ] 14.6 Abstract operations and coercion
- [ ] 14.7 ToPrimitive
- [ ] 14.8 ToBoolean
- [ ] 14.9 ToNumber
- [ ] 14.10 ToString
- [ ] 14.11 Relational comparison
- [ ] 14.12 Equality edge cases
- [ ] 14.13 Object identity
- [ ] 14.14 Reference behavior and mutation
- [ ] 14.15 Language specification terminology

## Module 15. Advanced Collections and Data Structures
- [ ] 15.1 Arrays: internal behavior and characteristics
- [ ] 15.2 Sparse arrays
- [ ] 15.3 Array-like objects
- [ ] 15.4 Typed arrays
- [ ] 15.5 ArrayBuffer
- [ ] 15.6 SharedArrayBuffer
- [ ] 15.7 DataView
- [ ] 15.8 Map
- [ ] 15.9 WeakMap
- [ ] 15.10 Set
- [ ] 15.11 WeakSet
- [ ] 15.12 Iteration behavior of collections
- [ ] 15.13 Choosing appropriate data structures
- [ ] 15.14 Time and space complexity of common operations
- [ ] 15.15 Building custom data structures in JavaScript

## Module 16. Iterators, Generators, and Iteration Protocols
- [ ] 16.1 Iteration fundamentals
- [ ] 16.2 Iterable protocol
- [ ] 16.3 Iterator protocol
- [ ] 16.4 `Symbol.iterator`
- [ ] 16.5 Custom iterators
- [ ] 16.6 Generator functions
- [ ] 16.7 The `yield` keyword
- [ ] 16.8 Generator execution and suspension
- [ ] 16.9 Generator return values
- [ ] 16.10 Delegation with `yield*`
- [ ] 16.11 Async iterators
- [ ] 16.12 Async generators
- [ ] 16.13 `Symbol.asyncIterator`
- [ ] 16.14 `for await...of`
- [ ] 16.15 Lazy evaluation
- [ ] 16.16 Practical generator applications

## Module 17. Metaprogramming and Reflection
- [ ] 17.1 Understanding metaprogramming
- [ ] 17.2 Property introspection
- [ ] 17.3 Reflection APIs
- [ ] 17.4 `Reflect` object
- [ ] 17.5 `Proxy` object
- [ ] 17.6 Proxy traps
- [ ] 17.7 Get and set interception
- [ ] 17.8 Property definition interception
- [ ] 17.9 Function interception
- [ ] 17.10 Proxy invariants
- [ ] 17.11 Revocable proxies
- [ ] 17.12 `Symbol` and well-known symbols
- [ ] 17.13 Customizing language behavior
- [ ] 17.14 Practical applications of metaprogramming

## Module 18. Error Handling and Exception Mechanics
- [ ] 18.1 Error handling fundamentals
- [ ] 18.2 Error objects
- [ ] 18.3 Built-in error types
- [ ] 18.4 `throw`
- [ ] 18.5 `try`, `catch`, and `finally`
- [ ] 18.6 Custom error classes
- [ ] 18.7 Error propagation
- [ ] 18.8 Stack traces
- [ ] 18.9 Synchronous vs. asynchronous errors
- [ ] 18.10 Promise rejection handling
- [ ] 18.11 Error boundaries in application architecture
- [ ] 18.12 Error classification
- [ ] 18.13 Defensive programming
- [ ] 18.14 Designing reliable error-handling strategies

## Module 19. Modules and JavaScript Architecture
- [ ] 19.1 Why modules exist
- [ ] 19.2 Module scope
- [ ] 19.3 CommonJS modules
- [ ] 19.4 ECMAScript modules (ESM)
- [ ] 19.5 `export` and `import`
- [ ] 19.6 Named exports
- [ ] 19.7 Default exports
- [ ] 19.8 Re-exports
- [ ] 19.9 Dynamic imports
- [ ] 19.10 Module resolution
- [ ] 19.11 Module caching
- [ ] 19.12 Module dependency graphs
- [ ] 19.13 Circular dependencies
- [ ] 19.14 Top-level `await`
- [ ] 19.15 Module initialization
- [ ] 19.16 CommonJS vs. ESM
- [ ] 19.17 Code organization
- [ ] 19.18 Separation of concerns
- [ ] 19.19 Dependency management and modular architecture

**Phase 3 practical outcome:** Build a modular utility library, custom collections, a small event system, and reusable abstractions.

---

# PHASE 4 --- Asynchronous JavaScript and Concurrency
**Objective:** Understand asynchronous execution deeply enough to build responsive browser applications and scalable Node.js applications.

## Module 20. Synchronous and Asynchronous Programming
- [ ] 20.1 Synchronous execution
- [ ] 20.2 Asynchronous execution
- [ ] 20.3 Blocking vs. non-blocking operations
- [ ] 20.4 Concurrency vs. parallelism
- [ ] 20.5 Callbacks
- [ ] 20.6 Callback patterns
- [ ] 20.7 Callback nesting
- [ ] 20.8 Callback hell
- [ ] 20.9 Inversion of control
- [ ] 20.10 Error-first callbacks
- [ ] 20.11 Event-driven programming
- [ ] 20.12 Event loop fundamentals

## Module 21. Event Loop --- Deep Internals
- [ ] 21.1 JavaScript's single-threaded execution model
- [ ] 21.2 Call stack
- [ ] 21.3 Heap
- [ ] 21.4 Host environment responsibilities
- [ ] 21.5 Task queues
- [ ] 21.6 Microtask queues
- [ ] 21.7 Macrotasks (task queues)
- [ ] 21.8 Event loop processing model
- [ ] 21.9 Task prioritization
- [ ] 21.10 Microtask checkpoints
- [ ] 21.11 Promise scheduling
- [ ] 21.12 `queueMicrotask()`
- [ ] 21.13 Rendering and event-loop interactions in browsers
- [ ] 21.14 Event loop starvation
- [ ] 21.15 Long-running synchronous tasks
- [ ] 21.16 Browser vs. Node.js event loops

## Module 22. Promises --- Complete Understanding
- [ ] 22.1 Why promises exist
- [ ] 22.2 Promise states
- [ ] 22.3 Promise lifecycle
- [ ] 22.4 Promise creation
- [ ] 22.5 Executor function
- [ ] 22.6 Resolve and reject
- [ ] 22.7 Promise chaining
- [ ] 22.8 `.then()`
- [ ] 22.9 `.catch()`
- [ ] 22.10 `.finally()`
- [ ] 22.11 Promise resolution procedure
- [ ] 22.12 Promise assimilation
- [ ] 22.13 Promise flattening
- [ ] 22.14 Promise error propagation
- [ ] 22.15 Promise composition
- [ ] 22.16 `Promise.all()`
- [ ] 22.17 `Promise.allSettled()`
- [ ] 22.18 `Promise.race()`
- [ ] 22.19 `Promise.any()`
- [ ] 22.20 Unhandled rejections

## Module 23. Async/Await and Advanced Asynchronous Patterns

- [ ] 23.1 `async` functions
- [ ] 23.2 `await` semantics
- [ ] 23.3 Async function return values
- [ ] 23.4 Error handling using `try/catch`
- [ ] 23.5 Sequential vs. parallel execution
- [ ] 23.6 Concurrent asynchronous operations
- [ ] 23.7 Promise orchestration
- [ ] 23.8 Async control flow
- [ ] 23.9 Race conditions
- [ ] 23.10 Promise-based retry mechanisms
- [ ] 23.11 Exponential backoff
- [ ] 23.12 Timeouts
- [ ] 23.13 Cancellation
- [ ] 23.14 AbortController and AbortSignal
- [ ] 23.15 Request deduplication
- [ ] 23.16 Concurrency limiting
- [ ] 23.17 Rate limiting
- [ ] 23.18 Debouncing and throttling
- [ ] 23.19 Async iterators and generators
- [ ] 23.20 Designing resilient async workflows

## Module 24. JavaScript Multithreading and Shared Memory

- [ ] 24.1 JavaScript agents
- [ ] 24.2 Main thread
- [ ] 24.3 Web Workers
- [ ] 24.4 Dedicated workers
- [ ] 24.5 Shared workers
- [ ] 24.6 Service workers
- [ ] 24.7 Worker communication
- [ ] 24.8 Structured cloning
- [ ] 24.9 Transferable objects
- [ ] 24.10 SharedArrayBuffer
- [ ] 24.11 Atomics
- [ ] 24.12 Race conditions
- [ ] 24.13 Synchronization
- [ ] 24.14 Message passing
- [ ] 24.15 Worker Threads in Node.js
- [ ] 24.16 CPU-bound vs. I/O-bound operations

**Phase 4 practical outcome:** Build a concurrent task scheduler, request manager, retry system, and worker-based computational application.

---

# PHASE 5 --- Browser JavaScript and Web Platform Engineering

**Objective:** Master the browser platform and build interactive web applications using vanilla JavaScript.

## Module 25. Browser Architecture and JavaScript Runtime

- [ ] 25.1 Browser architecture overview
- [ ] 25.2 Browser rendering process
- [ ] 25.3 JavaScript engine vs. browser engine
- [ ] 25.4 Browser runtime environment
- [ ] 25.5 Window and global objects
- [ ] 25.6 The `window` object
- [ ] 25.7 The `document` object
- [ ] 25.8 The `navigator` object
- [ ] 25.9 The `location` object
- [ ] 25.10 The `history` object
- [ ] 25.11 Browser event loop
- [ ] 25.12 JavaScript execution and rendering
- [ ] 25.13 Critical rendering path
- [ ] 25.14 Reflow and repaint
- [ ] 25.15 Browser developer tools

## Module 26. DOM --- Document Object Model

- [ ] 26.1 Understanding the DOM
- [ ] 26.2 DOM tree structure
- [ ] 26.3 DOM nodes and elements
- [ ] 26.4 Selecting elements
- [ ] 26.5 Traversing the DOM
- [ ] 26.6 Creating elements
- [ ] 26.7 Modifying elements
- [ ] 26.8 Removing elements
- [ ] 26.9 Attributes and properties
- [ ] 26.10 Classes and styles
- [ ] 26.11 DOM manipulation
- [ ] 26.12 DocumentFragment
- [ ] 26.13 HTML templates
- [ ] 26.14 Data attributes
- [ ] 26.15 DOM performance
- [ ] 26.16 Safe DOM manipulation

## Module 27. Browser Events and Event Architecture

- [ ] 27.1 Event-driven architecture
- [ ] 27.2 Browser event model
- [ ] 27.3 Event listeners
- [ ] 27.4 Event objects
- [ ] 27.5 Event propagation
- [ ] 27.6 Capturing phase
- [ ] 27.7 Target phase
- [ ] 27.8 Bubbling phase
- [ ] 27.9 Event delegation
- [ ] 27.10 `preventDefault()`
- [ ] 27.11 `stopPropagation()`
- [ ] 27.12 `stopImmediatePropagation()`
- [ ] 27.13 Event listener options
- [ ] 27.14 Custom events
- [ ] 27.15 Keyboard and pointer events
- [ ] 27.16 Form events
- [ ] 27.17 Event performance and memory management

## Module 28. Browser APIs and Client-Side Development

- [ ] 28.1 Web APIs vs. ECMAScript
- [ ] 28.2 Fetch API
- [ ] 28.3 XMLHttpRequest
- [ ] 28.4 Request and Response objects
- [ ] 28.5 HTTP request handling
- [ ] 28.6 Headers and body
- [ ] 28.7 AbortController
- [ ] 28.8 URL and URLSearchParams
- [ ] 28.9 FormData
- [ ] 28.10 Web Storage API
- [ ] 28.11 LocalStorage
- [ ] 28.12 SessionStorage
- [ ] 28.13 IndexedDB
- [ ] 28.14 Cookies
- [ ] 28.15 History API
- [ ] 28.16 Clipboard API
- [ ] 28.17 Geolocation API
- [ ] 28.18 WebSocket API
- [ ] 28.19 Server-Sent Events
- [ ] 28.20 Notifications API
- [ ] 28.21 File API and Blob
- [ ] 28.22 FileReader
- [ ] 28.23 Drag and Drop API
- [ ] 28.24 Intersection Observer
- [ ] 28.25 Mutation Observer
- [ ] 28.26 Resize Observer
- [ ] 28.27 Web Workers
- [ ] 28.28 Service Workers

## Module 29. Forms, Validation, and Browser Security

- [ ] 29.1 Form handling
- [ ] 29.2 Input validation
- [ ] 29.3 Native browser validation
- [ ] 29.4 Custom validation
- [ ] 29.5 FormData processing
- [ ] 29.6 File uploads
- [ ] 29.7 Client-side data sanitization
- [ ] 29.8 DOM-based Cross-Site Scripting (XSS)
- [ ] 29.9 Content Security Policy
- [ ] 29.10 Same-Origin Policy
- [ ] 29.11 Cross-Origin Resource Sharing (CORS)
- [ ] 29.12 Cross-site request forgery (CSRF)
- [ ] 29.13 Secure cookie attributes
- [ ] 29.14 Safe rendering and output encoding
- [ ] 29.15 Client-side security limitations

## Module 30. Browser Performance and Application Lifecycle

- [ ] 30.1 DOM performance
- [ ] 30.2 Layout thrashing
- [ ] 30.3 Reflow and repaint optimization
- [ ] 30.4 Rendering pipeline
- [ ] 30.5 Lazy loading
- [ ] 30.6 Resource loading
- [ ] 30.7 Debouncing and throttling in UI
- [ ] 30.8 RequestAnimationFrame
- [ ] 30.9 Performance API
- [ ] 30.10 Performance Observer
- [ ] 30.11 Memory leaks in browser applications
- [ ] 30.12 Page lifecycle
- [ ] 30.13 Visibility API
- [ ] 30.14 Page navigation
- [ ] 30.15 Offline capabilities
- [ ] 30.16 Progressive Web Application fundamentals

**Phase 5 practical outcome:** Build a vanilla JavaScript application with forms, dynamic UI, API communication, persistent storage, event delegation, and offline support.

---

# PHASE 6 --- JavaScript Runtime Internals and Performance Engineering

**Objective:** Understand how modern JavaScript engines execute, optimize, and manage JavaScript programs.

## Module 31. JavaScript Engine Internals

- [ ] 31.1 JavaScript engine architecture
- [ ] 31.2 Source-code processing
- [ ] 31.3 Lexical analysis
- [ ] 31.4 Parsing
- [ ] 31.5 Abstract Syntax Trees (AST)
- [ ] 31.6 Bytecode generation
- [ ] 31.7 Interpreter execution
- [ ] 31.8 Just-In-Time compilation
- [ ] 31.9 Baseline compilation
- [ ] 31.10 Optimizing compilation
- [ ] 31.11 Runtime profiling
- [ ] 31.12 Speculative optimization
- [ ] 31.13 Deoptimization
- [ ] 31.14 Inline caching
- [ ] 31.15 Hidden classes / shapes
- [ ] 31.16 Property access optimization
- [ ] 31.17 Function optimization
- [ ] 31.18 Engine-specific behavior

## Module 32. Memory Management and Garbage Collection

- [ ] 32.1 JavaScript memory model
- [ ] 32.2 Stack and heap
- [ ] 32.3 Memory allocation
- [ ] 32.4 Object lifetime
- [ ] 32.5 Reachability
- [ ] 32.6 Garbage collection fundamentals
- [ ] 32.7 Reference counting vs. tracing
- [ ] 32.8 Mark-and-sweep
- [ ] 32.9 Generational garbage collection
- [ ] 32.10 Incremental garbage collection
- [ ] 32.11 Concurrent garbage collection
- [ ] 32.12 Memory leaks
- [ ] 32.13 Detached DOM nodes
- [ ] 32.14 Closure-related memory retention
- [ ] 32.15 Weak references
- [ ] 32.16 WeakRef
- [ ] 32.17 FinalizationRegistry
- [ ] 32.18 Memory profiling
- [ ] 32.19 Heap snapshots
- [ ] 32.20 Memory optimization strategies

## Module 33. JavaScript Performance Engineering

- [ ] 33.1 Understanding performance
- [ ] 33.2 Algorithmic complexity
- [ ] 33.3 Time and space complexity
- [ ] 33.4 Profiling JavaScript
- [ ] 33.5 Benchmarking
- [ ] 33.6 Avoiding misleading benchmarks
- [ ] 33.7 JIT-friendly coding
- [ ] 33.8 Object shape consistency
- [ ] 33.9 Function optimization considerations
- [ ] 33.10 DOM performance
- [ ] 33.11 Memory allocation reduction
- [ ] 33.12 Asynchronous performance
- [ ] 33.13 Event-loop latency
- [ ] 33.14 CPU profiling
- [ ] 33.15 Flame graphs
- [ ] 33.16 Performance budgets
- [ ] 33.17 Identifying bottlenecks
- [ ] 33.18 Measuring before optimizing

## Module 34. Advanced Language Features and Specification Awareness

- [ ] 34.1 ECMAScript specification structure
- [ ] 34.2 Abstract operations
- [ ] 34.3 Internal slots
- [ ] 34.4 Internal methods
- [ ] 34.5 Property access semantics
- [ ] 34.6 Completion records
- [ ] 34.7 Abrupt completions
- [ ] 34.8 Iterator closing
- [ ] 34.9 Promise jobs
- [ ] 34.10 Jobs and host hooks
- [ ] 34.11 Realms
- [ ] 34.12 Agents
- [ ] 34.13 Symbols and well-known symbols
- [ ] 34.14 Explicit resource management (`using` and `await using`)
- [ ] 34.15 Feature compatibility
- [ ] 34.16 TC39 proposal stages
- [ ] 34.17 Reading specification algorithms
- [ ] 34.18 Cross-engine differences

**Phase 6 practical outcome:** Profile and optimize applications, investigate memory leaks, analyze engine behavior, and explain performance characteristics.

---

# PHASE 7 --- Node.js and Backend JavaScript Engineering

**Objective:** Become capable of developing production-oriented backend applications using JavaScript and Node.js.

## Module 35. Node.js Fundamentals and Architecture

- [ ] 35.1 What is Node.js?
- [ ] 35.2 Node.js architecture
- [ ] 35.3 V8 engine and Node.js
- [ ] 35.4 Libuv
- [ ] 35.5 Node.js runtime environment
- [ ] 35.6 Node.js APIs vs. ECMAScript APIs
- [ ] 35.7 Node.js installation and environment
- [ ] 35.8 Node.js REPL
- [ ] 35.9 Running JavaScript scripts
- [ ] 35.10 Node.js process lifecycle
- [ ] 35.11 The `process` object
- [ ] 35.12 Environment variables
- [ ] 35.13 Command-line arguments
- [ ] 35.14 Node.js global objects
- [ ] 35.15 Debugging Node.js applications

## Module 36. Node.js Modules and Package Management

- [ ] 36.1 CommonJS module system
- [ ] 36.2 ECMAScript modules in Node.js
- [ ] 36.3 `require()` and `module.exports`
- [ ] 36.4 `import` and `export`
- [ ] 36.5 Module resolution
- [ ] 36.6 Module caching
- [ ] 36.7 Package structure
- [ ] 36.8 npm fundamentals
- [ ] 36.9 `package.json`
- [ ] 36.10 Dependencies and devDependencies
- [ ] 36.11 Semantic versioning
- [ ] 36.12 package-lock.json
- [ ] 36.13 npm scripts
- [ ] 36.14 Dependency installation
- [ ] 36.15 Dependency management
- [ ] 36.16 npm workspaces
- [ ] 36.17 Publishing reusable packages
- [ ] 36.18 Supply-chain security fundamentals

## Module 37. Node.js Core APIs

- [ ] 37.1 File system (`fs`)
- [ ] 37.2 Path (`path`)
- [ ] 37.3 Operating system (`os`)
- [ ] 37.4 Process (`process`)
- [ ] 37.5 Events (`events`)
- [ ] 37.6 EventEmitter
- [ ] 37.7 Buffers
- [ ] 37.8 Streams
- [ ] 37.9 HTTP
- [ ] 37.10 HTTPS
- [ ] 37.11 Crypto
- [ ] 37.12 URL
- [ ] 37.13 Timers
- [ ] 37.14 DNS
- [ ] 37.15 Networking (`net`)
- [ ] 37.16 Compression (`zlib`)
- [ ] 37.17 Child processes
- [ ] 37.18 Worker threads
- [ ] 37.19 Readline
- [ ] 37.20 Utilities (`util`)

## Module 38. Node.js Asynchronous Internals

- [ ] 38.1 Node.js event loop
- [ ] 38.2 Event-loop phases
- [ ] 38.3 Timers phase
- [ ] 38.4 Pending callbacks
- [ ] 38.5 Poll phase
- [ ] 38.6 Check phase
- [ ] 38.7 Close callbacks
- [ ] 38.8 `setImmediate()`
- [ ] 38.9 `setTimeout()`
- [ ] 38.10 `process.nextTick()`
- [ ] 38.11 Promise microtasks
- [ ] 38.12 Libuv thread pool
- [ ] 38.13 Asynchronous I/O
- [ ] 38.14 Worker pool
- [ ] 38.15 Event-loop starvation
- [ ] 38.16 Blocking operations
- [ ] 38.17 CPU-intensive workloads
- [ ] 38.18 Node.js concurrency model

## Module 39. Streams, Buffers, and Data Processing

- [ ] 39.1 Binary data fundamentals
- [ ] 39.2 Buffer creation
- [ ] 39.3 Buffer operations
- [ ] 39.4 Encoding and decoding
- [ ] 39.5 Stream fundamentals
- [ ] 39.6 Readable streams
- [ ] 39.7 Writable streams
- [ ] 39.8 Duplex streams
- [ ] 39.9 Transform streams
- [ ] 39.10 Stream piping
- [ ] 39.11 Backpressure
- [ ] 39.12 Stream error handling
- [ ] 39.13 Object-mode streams
- [ ] 39.14 Async iteration over streams
- [ ] 39.15 File streaming
- [ ] 39.16 HTTP streaming
- [ ] 39.17 Efficient large-file processing

## Module 40. HTTP and Networking Fundamentals

- [ ] 40.1 Client-server architecture
- [ ] 40.2 HTTP request-response cycle
- [ ] 40.3 HTTP methods
- [ ] 40.4 HTTP status codes
- [ ] 40.5 Request headers
- [ ] 40.6 Response headers
- [ ] 40.7 Request body
- [ ] 40.8 Content types
- [ ] 40.9 HTTP caching
- [ ] 40.10 Cookies and sessions
- [ ] 40.11 HTTP persistent connections
- [ ] 40.12 HTTPS and TLS fundamentals
- [ ] 40.13 TCP fundamentals
- [ ] 40.14 DNS resolution
- [ ] 40.15 WebSockets
- [ ] 40.16 REST architectural principles
- [ ] 40.17 API communication
- [ ] 40.18 Network failure handling

## Module 41. Express.js --- Framework Fundamentals

- [ ] 41.1 Introduction to Express.js
- [ ] 41.2 Express architecture
- [ ] 41.3 Application setup
- [ ] 41.4 Request and response objects
- [ ] 41.5 Routing
- [ ] 41.6 Route parameters
- [ ] 41.7 Query parameters
- [ ] 41.8 Request body parsing
- [ ] 41.9 Middleware architecture
- [ ] 41.10 Application-level middleware
- [ ] 41.11 Router-level middleware
- [ ] 41.12 Built-in middleware
- [ ] 41.13 Third-party middleware
- [ ] 41.14 Custom middleware
- [ ] 41.15 Middleware execution order
- [ ] 41.16 Route handlers
- [ ] 41.17 Route chaining
- [ ] 41.18 Error-handling middleware
- [ ] 41.19 Static file serving
- [ ] 41.20 Express application configuration

## Module 42. Backend API Development

- [ ] 42.1 REST API design
- [ ] 42.2 Resource-oriented endpoints
- [ ] 42.3 HTTP methods and semantics
- [ ] 42.4 Request validation
- [ ] 42.5 Response formatting
- [ ] 42.6 Status code conventions
- [ ] 42.7 Pagination
- [ ] 42.8 Filtering and sorting
- [ ] 42.9 API versioning
- [ ] 42.10 Authentication
- [ ] 42.11 Authorization
- [ ] 42.12 Role-based access control
- [ ] 42.13 Session-based authentication
- [ ] 42.14 Token-based authentication
- [ ] 42.15 JWT fundamentals
- [ ] 42.16 Password hashing
- [ ] 42.17 Rate limiting
- [ ] 42.18 CORS configuration
- [ ] 42.19 API documentation
- [ ] 42.20 Error response standards

## Module 43. Databases and Data Access from Node.js

- [ ] 43.1 Database fundamentals
- [ ] 43.2 Relational vs. NoSQL databases
- [ ] 43.3 SQL fundamentals
- [ ] 43.4 PostgreSQL integration
- [ ] 43.5 Database drivers
- [ ] 43.6 Connection management
- [ ] 43.7 Connection pooling
- [ ] 43.8 CRUD operations
- [ ] 43.9 Parameterized queries
- [ ] 43.10 SQL injection prevention
- [ ] 43.11 Transactions
- [ ] 43.12 ACID properties
- [ ] 43.13 Isolation levels
- [ ] 43.14 Database indexes
- [ ] 43.15 Query optimization
- [ ] 43.16 Database migrations
- [ ] 43.17 Data validation
- [ ] 43.18 Repository pattern
- [ ] 43.19 Object-relational mapping fundamentals
- [ ] 43.20 Redis fundamentals and caching

## Module 44. Production Backend Engineering

- [ ] 44.1 Layered architecture
- [ ] 44.2 Separation of concerns
- [ ] 44.3 Controller-service-repository architecture
- [ ] 44.4 Dependency injection
- [ ] 44.5 Configuration management
- [ ] 44.6 Environment separation
- [ ] 44.7 Structured logging
- [ ] 44.8 Error monitoring
- [ ] 44.9 Health checks
- [ ] 44.10 Graceful shutdown
- [ ] 44.11 Process management
- [ ] 44.12 Clustering
- [ ] 44.13 Horizontal scaling
- [ ] 44.14 Stateless application design
- [ ] 44.15 Caching strategies
- [ ] 44.16 Background jobs
- [ ] 44.17 Message queues
- [ ] 44.18 Idempotency
- [ ] 44.19 Retry strategies
- [ ] 44.20 Distributed systems fundamentals

**Phase 7 practical outcome:** Build a modular REST API with Express, PostgreSQL, authentication, authorization, validation, logging, error handling, and production-oriented configuration.

---

# PHASE 8 --- Professional JavaScript Development and Engineering Practices

**Objective:** Develop the engineering practices required to work effectively on real-world JavaScript codebases.

## Module 45. JavaScript Design Patterns
- [ ] 45.1 What are design patterns?
- [ ] 45.2 Creational patterns
- [ ] 45.3 Factory pattern
- [ ] 45.4 Constructor pattern
- [ ] 45.5 Singleton pattern
- [ ] 45.6 Builder pattern
- [ ] 45.7 Structural patterns
- [ ] 45.8 Adapter pattern
- [ ] 45.9 Decorator pattern
- [ ] 45.10 Facade pattern
- [ ] 45.11 Proxy pattern
- [ ] 45.12 Behavioral patterns
- [ ] 45.13 Observer pattern
- [ ] 45.14 Pub/Sub pattern
- [ ] 45.15 Strategy pattern
- [ ] 45.16 Command pattern
- [ ] 45.17 Module pattern
- [ ] 45.18 Dependency injection
- [ ] 45.19 Composition over inheritance
- [ ] 45.20 When not to use design patterns

## Module 46. Functional Programming in JavaScript
- [ ] 46.1 Functional programming fundamentals
- [ ] 46.2 First-class functions
- [ ] 46.3 Pure functions
- [ ] 46.4 Immutability
- [ ] 46.5 Referential transparency
- [ ] 46.6 Higher-order functions
- [ ] 46.7 Function composition
- [ ] 46.8 Currying
- [ ] 46.9 Partial application
- [ ] 46.10 Closures in functional design
- [ ] 46.11 Declarative vs. imperative programming
- [ ] 46.12 Side-effect management
- [ ] 46.13 Data transformation pipelines
- [ ] 46.14 Functional error handling
- [ ] 46.15 Functional programming trade-offs

## Module 47. Testing and Quality Assurance
- [ ] 47.1 Software testing fundamentals
- [ ] 47.2 Unit testing
- [ ] 47.3 Integration testing
- [ ] 47.4 End-to-end testing
- [ ] 47.5 Test-driven development
- [ ] 47.6 Node.js built-in test runner
- [ ] 47.7 Assertion libraries
- [ ] 47.8 Mocking
- [ ] 47.9 Stubbing
- [ ] 47.10 Spying
- [ ] 47.11 Test doubles
- [ ] 47.12 Testing asynchronous code
- [ ] 47.13 Testing API endpoints
- [ ] 47.14 Testing error scenarios
- [ ] 47.15 Test coverage
- [ ] 47.16 Regression testing
- [ ] 47.17 Debugging and test isolation

## Module 48. Development Tooling and Code Quality
- [ ] 48.1 Browser DevTools
- [ ] 48.2 Node.js debugging
- [ ] 48.3 Breakpoints and watch expressions
- [ ] 48.4 Stack traces
- [ ] 48.5 Source maps
- [ ] 48.6 ESLint
- [ ] 48.7 Prettier
- [ ] 48.8 Git and version control
- [ ] 48.9 npm scripts
- [ ] 48.10 Build tools overview
- [ ] 48.11 Bundlers: Vite, esbuild, and Webpack
- [ ] 48.12 Transpilation
- [ ] 48.13 Babel fundamentals
- [ ] 48.14 Tree shaking
- [ ] 48.15 Code splitting
- [ ] 48.16 Minification
- [ ] 48.17 Environment configuration
- [ ] 48.18 CI fundamentals

## Module 49. Application Security
- [ ] 49.1 Secure JavaScript coding practices
- [ ] 49.2 Input validation
- [ ] 49.3 Output encoding
- [ ] 49.4 XSS
- [ ] 49.5 CSRF
- [ ] 49.6 CORS
- [ ] 49.7 Prototype pollution
- [ ] 49.8 Dependency vulnerabilities
- [ ] 49.9 Authentication security
- [ ] 49.10 Authorization flaws
- [ ] 49.11 Session management
- [ ] 49.12 Password storage
- [ ] 49.13 Secret management
- [ ] 49.14 Injection vulnerabilities
- [ ] 49.15 Denial-of-service considerations
- [ ] 49.16 Secure HTTP headers
- [ ] 49.17 Security auditing
- [ ] 49.18 Threat modeling

## Module 50. Scalable Application Architecture
- [ ] 50.1 Software architecture fundamentals
- [ ] 50.2 Monolithic architecture
- [ ] 50.3 Modular monoliths
- [ ] 50.4 Microservices fundamentals
- [ ] 50.5 Domain-driven design fundamentals
- [ ] 50.6 Domain modeling
- [ ] 50.7 Layered architecture
- [ ] 50.8 Hexagonal architecture
- [ ] 50.9 Clean architecture
- [ ] 50.10 Event-driven architecture
- [ ] 50.11 Message-driven systems
- [ ] 50.12 Distributed caching
- [ ] 50.13 Database scaling
- [ ] 50.14 Horizontal scaling
- [ ] 50.15 Observability
- [ ] 50.16 Fault tolerance
- [ ] 50.17 Resilience patterns
- [ ] 50.18 System design for JavaScript applications

## Module 51. Deployment and Operations
- [ ] 51.1 Production build fundamentals
- [ ] 51.2 Environment variables
- [ ] 51.3 Linux server fundamentals
- [ ] 51.4 Process management
- [ ] 51.5 Reverse proxies
- [ ] 51.6 Nginx fundamentals
- [ ] 51.7 Docker fundamentals
- [ ] 51.8 Containerizing Node.js applications
- [ ] 51.9 CI/CD
- [ ] 51.10 Deployment strategies
- [ ] 51.11 Cloud deployment fundamentals
- [ ] 51.12 Logging and monitoring
- [ ] 51.13 Application metrics
- [ ] 51.14 Distributed tracing
- [ ] 51.15 Production debugging
- [ ] 51.16 Performance monitoring
- [ ] 51.17 Rollbacks
- [ ] 51.18 Application maintenance

**Phase 8 practical outcome:** Design, test, secure, deploy, and maintain production-quality JavaScript applications.

---

# CAPSTONE PROJECTS

Projects integrate the concepts from multiple phases. They do not replace chapter exercises or assessments.

## Project 1 --- Advanced Task Management Application

**Focus:** Browser JavaScript.

- [ ] DOM architecture and event delegation
- [ ] State management without frameworks
- [ ] LocalStorage and IndexedDB
- [ ] Asynchronous API communication
- [ ] Modular application design
- [ ] Form handling and validation
- [ ] Error states and accessibility considerations
- [ ] Testing and documentation

## Project 2 --- Real-Time Analytics Dashboard

**Focus:** Advanced browser APIs.

- [ ] Fetch and WebSocket
- [ ] Asynchronous data pipelines
- [ ] Web Workers
- [ ] Performance optimization
- [ ] Real-time UI updates
- [ ] Cancellation and reconnection strategies
- [ ] Rendering and memory profiling
- [ ] Failure-state handling

## Project 3 --- Production REST API

**Focus:** Node.js and Express.js.

- [ ] Authentication and role-based access control
- [ ] PostgreSQL integration
- [ ] Middleware and request validation
- [ ] Centralized error handling
- [ ] Automated testing
- [ ] Structured logging
- [ ] Security controls
- [ ] Deployment and operational documentation

## Project 4 --- Full-Stack E-commerce System

**Focus:** Final engineering project.

- [ ] Vanilla JavaScript frontend
- [ ] Node.js and Express backend
- [ ] PostgreSQL
- [ ] Cart, orders, and inventory
- [ ] Payment integration concepts (use a payment provider's test environment; do not store card data)
- [ ] Authentication and authorization
- [ ] Security and scalability
- [ ] Testing and observability
- [ ] Deployment and maintenance documentation

**Constraint:** Build the frontend without React or another frontend framework. The purpose is to demonstrate that the underlying browser and JavaScript fundamentals are understood.

---

# RECOMMENDED LEARNING SEQUENCE AND TIME ALLOCATION

A reasonable first-pass planning estimate is **30--36 weeks**, depending on prior knowledge, implementation speed, and the depth of assessments.

---

Phase Primary Difficulty Suggested duration competency

---

Phase 1 Language Beginner 3 weeks foundations

Phase 2 Functions, Intermediate 4 weeks scope, and  
object model

Phase 3 Advanced Advanced 4 weeks language and  
internals

Phase 4 Asynchronous Advanced 3 weeks programming

Phase 5 Browser and Web Intermediate--Advanced 4 weeks APIs

Phase 6 Engine internals Expert 3 weeks and performance

Phase 7 Node.js and Advanced 5 weeks backend  
engineering

Phase 8 Professional Expert 4 weeks engineering

## Revision and Integration and Advanced--Expert 2--6 weeks capstones independent  
delivery

This is a planning estimate, not a deadline. Mastery takes priority over completing chapters quickly.

---

# MASTERY ASSESSMENT FRAMEWORK

For every module, assess the learner across these dimensions:

---

Dimension Evidence of mastery

---

Conceptual accuracy Definitions, distinctions, and correct mental models

Mechanistic understanding Can explain execution and runtime behavior

Code tracing Can predict outputs and explain each step

Implementation Can write working code independently

Debugging Can isolate and fix defects and edge cases

## Engineering judgment Can explain trade-offs and select appropriate approaches

### Critical topics requiring L5 mastery

- [ ] Scope, hoisting, and the Temporal Dead Zone
- [ ] Functions, higher-order functions, and closures
- [ ] Execution contexts and call stack
- [ ] `this` binding and invocation rules
- [ ] Objects, property descriptors, prototypes, and inheritance
- [ ] Equality, coercion, and language semantics
- [ ] Iterators, generators, and metaprogramming fundamentals
- [ ] Promises, async/await, and error propagation
- [ ] Browser and Node.js event loops
- [ ] Concurrency, cancellation, and race conditions
- [ ] DOM events and browser API integration
- [ ] JavaScript memory management and profiling
- [ ] Node.js streams and backpressure
- [ ] Express middleware and error handling
- [ ] HTTP, authentication, authorization, and security
- [ ] Database transactions and data-access design
- [ ] Testing, observability, and application architecture

### Module completion record

For each module, record:

- **Module:**
- **Date started / completed:**
- **Chapters completed:**
- **Code exercises completed:**
- **Assessment result:**
- **Strong concepts:**
- **Weak concepts:**
- **Concepts to revisit:**
- **Mastery level (L1--L5):**
- **Independent implementation:**

Do not mark a module complete merely because its chapters were read. Completion requires an assessment and practical evidence.

---

# OFFICIAL DOCUMENTATION AND REFERENCE LIBRARY

Use official documentation as the source of truth. Tutorials and videos may supplement it, but should not replace it.

## 1. MDN Web Docs --- JavaScript

**Primary language guide and reference.**

- [JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
- [JavaScript execution model](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Execution_model)
- [Web APIs](https://developer.mozilla.org/en-US/docs/Web/API)
- [DOM documentation](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
- [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
- [Performance](https://developer.mozilla.org/en-US/docs/Web/Performance)

## 2. ECMAScript Specification --- ECMA-262

**Normative language specification.**

- [ECMA-262 specification](https://tc39.es/ecma262/)
- [TC39 proposals](https://github.com/tc39/proposals)

Use the specification for precise semantics, abstract operations, internal methods, execution algorithms, and language behavior. It is a reference for deeper study, not the first resource to read for every topic.

## 3. V8 --- JavaScript Engine

**Engine internals and performance.**

- [V8 documentation](https://v8.dev/docs)
- [V8 blog](https://v8.dev/blog)

Use these resources for engine architecture, compilation, optimization, garbage collection, and performance investigations. V8 behavior is implementation-specific and should not be mistaken for a universal ECMAScript guarantee.

## 4. Node.js Documentation

**Runtime, APIs, and backend foundations.**

- [Node.js API documentation](https://nodejs.org/docs/latest/api/)
- [Node.js Learn](https://nodejs.org/learn)
- [Node.js event loop guide](https://nodejs.org/en/learn/asynchronous-work/event-loop-timers-and-nexttick)
- [Don't block the event loop](https://nodejs.org/en/learn/asynchronous-work/dont-block-the-event-loop)

## 5. Express.js Documentation

**Backend framework and HTTP application development.**

- [Express Guide](https://expressjs.com/en/guide/)
- [Express API reference](https://expressjs.com/en/5x/api.html)
- [Express middleware guide](https://expressjs.com/en/guide/using-middleware.html)
- [Express error handling](https://expressjs.com/en/guide/error-handling.html)

Check the documentation for the Express major version used in a project. Middleware behavior and APIs can differ across major versions.

## 6. JavaScript.info

**Structured supplementary tutorial and exercises.**

- [The Modern JavaScript Tutorial](https://javascript.info/)

Use it for supplementary explanations and practice. Verify version-sensitive details against MDN and the relevant official specifications.

---

# CURRICULUM SCOPE AND IMPORTANT DISTINCTIONS

1. **JavaScript before frameworks:** React and other frontend frameworks are intentionally excluded. First master JavaScript, DOM manipulation, browser APIs, asynchronous programming, and application architecture.
2. **Internals are included:** Execution contexts, lexical environments, prototypes, garbage collection, JIT compilation, event loops, and runtime architecture are part of the curriculum.
3. **Browser and backend are both essential:** Node.js alone is not sufficient for broad web-development competence. Browser execution, DOM, networking, storage, events, and rendering are equally important.
4. **Advanced does not mean always used:** Understand Proxy, WeakRef, Atomics, specification algorithms, and other specialized features, but learn when they are appropriate rather than forcing them into ordinary applications.
5. **TypeScript is deferred:** This curriculum focuses on JavaScript. TypeScript should be studied as a separate next step after strong JavaScript foundations.
6. **Documentation-first learning:** Use official references, experiments, code tracing, and independent implementations to validate understanding.
7. **No false mastery:** Reading, watching, or recognizing a concept is not sufficient evidence of mastery. Demonstrate it through explanation, code, debugging, and practical application.

---

# FINAL COMPLETION STANDARD

The curriculum is complete when the learner can:

- Explain JavaScript's core language semantics and runtime behavior.
- Write idiomatic JavaScript without relying on a framework.
- Reason about scope, closures, prototypes, object identity, and asynchronous execution.
- Understand browser APIs and build interactive browser applications.
- Explain relevant JavaScript engine and memory-management behavior.
- Build and test Node.js and Express.js backend services.
- Integrate databases and design reliable HTTP APIs.
- Identify and address common performance and security problems.
- Design, test, deploy, and maintain a complete web application.
- Defend technical decisions and debug unfamiliar problems independently.

**End goal:** Become an independent JavaScript engineer with strong language fundamentals, runtime understanding, browser development ability, and production-oriented backend engineering skills.