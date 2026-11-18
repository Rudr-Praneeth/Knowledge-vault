# Tuples
TAGS: #Python 
BUILT-ON: [[Data Structures]]
ENABLES: - 
PREREQUSITIES: - 

---
# Tuples
A tuple is a built-in Python data structure which is an ordered, immutable collection of objects.
Tuples can be used as dictionary keys and set elements when their contents are hashable. Lists are mutable and unhashable. A tuple, when all its elements are hashable, can be hashable. 
Tuples are generally more memory-efficient than equivalent lists in CPython because they have a fixed size and do not need the same capacity-management strategy used by dynamically growing lists. Use tuples primarily for their semantics, fixed structure and immutability, not as a premature optimization.

#### ~={purple}***Characteristics of Tuples***=~
- ***Collection of Objects***: References of multiple objects stored under a single name.
- ***Duplicate-Friendly***: Tuples allow insertion of duplicate elements.
- ***Heterogeneous Elements***: Tuples can store objects of different data types.
- ***Immutable***: Collection cannot be modified after creation.
- ***Ordered***: Elements in the tuple are positioned and preserve their relative order.
- ***Indexed***: Elements in a tuples can be accessed using indices. A tuple uses zero-based indexing.
  Attempting to access an index outside the valid range raises `IndexError`.

#### ~={purple}***Creation of Tuple***=~
Python allows multiple ways in which tuples can be created. They are as follows:
1. ***Using Parenthesis with comma***:
   ```python
   TUPLE = (*ELEMENT,..)
   
   VARIABLE = (ELEMENT) 
   #NOTE: NOT CONSIDERED AS SINGLE-ELEMENT TUPLE
   #      INSTEAD CONSIDERED AS AN VARIABLE
   
   TUPLE = (ELEMENT,)
   TUPLE = ELEMENT, ELEMENT, ELEMENT
   #NOTE: CONSIDERED AS A SINGLE-ELEMENT TUPLE
   #      IMPORTANT DETAIL BEING COMMA MAKES AN TUPLE. 
   #      PARENTHESIS ARE OPTIONAL AND HELP IMPROVE READABILITY 
   ```
2. **Using `tuple` Constructor**:
   ```python
   LIST = tuple(ITERABLE)
   
   ITERABLE = (ELEMENT, ELEMENT, ELEMENT) | STRING
   ```

#### ~={purple}***Accessing Tuple Elements***=~
1. ***Zero-based Indexing***: A tuple uses zero-based indexing: the first element has index `0`. 
   Attempting to access an index outside the valid range raises `IndexError`.
   `ELEMENT = TUPLE[INDEX]`
2. ***Negative indexing***: Negative indexing access tuple elements from the end
   Negative indexing is useful when the position of interest is relative to the end, such as the most recent item.
   `ELEMENT = TUPLE[-INDEX]`
3. ***Slice Indexing***: Slice indexing retrieves a section of a tuple by specifying the starting index, stopping index, and step size. It returns a new tuple containing the selected elements.
   `SUB_LIST = TUPLE[START: STOP: STEP]`
   - `START`: Index to begin slicing from (inclusive; defaults to the beginning).
   - `STOP`: Index to stop slicing at (exclusive; defaults to the end).
   - `STEP`: Interval between selected elements (defaults to `1`; can be negative to traverse backwards).

#### ~={purple}***Tuple Packing and Unpacking***=~:
**Tuple packing** means combining multiple values into a single tuple.
**Tuple unpacking** means assigning the individual elements of a tuple to separate variables. Python assigns each tuple element to the corresponding variable based on position. The number of variables must match the number of elements in ordinary unpacking. Python raises a `ValueError` because the number of values does not match the number of target variables.
```python
#TUPLE PACKING: PACKING N ELEMENTS IN TUPLE
TUPLE_COLLECTION = ELEMENT, ELEMENT, ELEMENT,...

#TUPLE UNPACKING: N-SIZED TUPLE
VARIABLE_1, VARIABLE_2, ... = TUPLE
```
Python supports starred unpacking, which allows one variable to capture multiple remaining values in a list.
```python
FIRST, MIDDLE*, LAST = TUPLE
# FIRST RECEIVES FIRST ELEMENT
# MIDDLE RECEIVES LIST OF ALL ELEMENTS EXCLUDING FIRST AND LAST
# LAST RECEIVES LAST ELEMENT

BEGINNING*, LAST = TUPLE
FIRST, REST* = TUPLE
```

#### ~={purple}***Tuple Operations***=~

| Operation                                 | Use Case                                                                 | Argument Types                                                        | Return Type               |
| ----------------------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------------- | ------------------------- |
| ~={cyan}**Element Position Search**=~     |                                                                          |                                                                       |                           |
| `index(VALUE, *START, *STOP)`             | Find the index of the first matching value within the optional range     | `VALUE: Any`, `START: Integer (optional)`, `STOP: Integer (optional)` | `Integer`                 |
| `count(VALUE)`                            | Count occurrences of a value                                             | `VALUE: Any`                                                          | `Integer`                 |
| ~={cyan}**Element Arrangement**=~         |                                                                          |                                                                       |                           |
| ~={cyan}**Collection Copy**=~             |                                                                          |                                                                       |                           |
| `copy()`                                  | Create a shallow copy of the tuple                                       | None                                                                  | `Tuple`                   |
| ~={cyan}**Additional Tuple Operations**=~ |                                                                          |                                                                       |                           |
| `__add__(OTHER)`                          | Concatenate two tuples using the `+` operator                            | `OTHER: Tuple`                                                        | `Tuple`                   |
| `__mul__(COUNT)`                          | Repeat the Tuple using the `*` operator                                  | `COUNT: Integer`                                                      | `Tuple`                   |
| `__rmul__(COUNT)`                         | Repeat the Tuple when the integer is on the left, e.g. `3 * items`       | `COUNT: Integer`                                                      | `Tuple`                   |
| `sorted(TUPLE, *KEY, *REVERSE)`           | Sort the tuple in place using an optional key function and reverse order | `KEY: Callable (optional)`, `REVERSE: Boolean (optional)`             | `List`                    |
| `__getitem__(INDEX_OR_SLICE)`             | Retrieve an element or a slice using indexing                            | `INDEX_OR_SLICE: Integer or Slice`                                    | `Element Type` or `Tuple` |
| `__contains__(VALUE)`                     | Check membership using `in`                                              | `VALUE: Any`                                                          | `Boolean`                 |
| `__iter__()`                              | Return an iterator over the Tuple                                        | None                                                                  | `Iterator`                |
| `__reversed__()`                          | Return a reverse iterator                                                | None                                                                  | `Iterator`                |
| `__len__()`                               | Return the number of elements using `len()`                              | None                                                                  | `Integer`                 |
| `__eq__(OTHER)`                           | Compare Tuple for equality using `==`                                    | `OTHER: Any`                                                          | `Boolean`                 |
| `__ne__(OTHER)`                           | Compare Tuple for inequality using `!=`                                  | `OTHER: Any`                                                          | `Boolean`                 |
| `__lt__(OTHER)`                           | Compare Tuple using `<` lexicographically                                | `OTHER: Tuple`                                                        | `Boolean`                 |
| `__le__(OTHER)`                           | Compare Tuple using `<=` lexicographically                               | `OTHER: Tuple`                                                        | `Boolean`                 |
| `__gt__(OTHER)`                           | Compare Tuple using `>` lexicographically                                | `OTHER: Tuple`                                                        | `Boolean`                 |
| `__ge__(OTHER)`                           | Compare Tuple using `>=` lexicographically                               | `OTHER: Tuple`                                                        | `Boolean`                 |
| `__repr__()`                              | Return the official string representation of the Tuple                   | None                                                                  | `String`                  |
| `__str__()`                               | Return the string representation of the Tuple                            | None                                                                  | `String`                  |
| `__sizeof__()`                            | Return the shallow size of the Tuple object in bytes                     | None                                                                  | `Integer`                 |

Notes: 
- `Iterable` means an object that can provide its elements one at a time, such as a list, tuple, string, or generator.
- `KEY` must be a callable that accepts a list element and returns a value used for sorting.
- The dunder methods (`__method__`) are special methods, usually invoked indirectly by operators or built-in functions. They are included for completeness but are not normally called directly.
- `__sizeof__()` reports the object's shallow memory size, not the total memory occupied by all nested elements.

#### ~={purple}***Tuple Iterations***=~
**Direct Iteration**:
```python
for ELEMENT in TUPLE:
	WORK()
```
**Iterating with Indices**
```python
for INDEX in RANGE(LEN(LIST)):
	WORK(TUPLE[INDEX])

for INDEX, ELEMENT in enumerate(LIST):
	WORK()
```

#### ~={purple}Tuple Time Complexities=~
- `ELEMENT in TUPLE`: $\Theta(n)$ worst case
- `TUPLE.index(ELEMENT)`: $\Theta(n)$ worst case
- `TUPLE.count(ELEMENT)`: $\Theta(n)$
- `TUPLE[i]`: $\Theta(1)$
- `TUPLE[i:j]`: $\Theta(k)$, where k is the number of elements in the resulting slice
- `TUPLE + OTHER_TUPLE`: $\Theta(n + m)$
- `TUPLE * COUNT`: $\Theta(n \cdot k)$, where $k = \max(0, COUNT)$
- `len(TUPLE)`: $\Theta(1)$
- `iter(TUPLE)`: $\Theta(1)$
- `reversed(TUPLE)`: $\Theta(1)$
- `TUPLE == OTHER_TUPLE`: \(O(n)\) worst case
- `tuple(TUPLE)`: $\Theta(1)$ for an existing tuple (typically returns the same object)
- `min(TUPLE)` or `max(TUPLE)`: $\Theta(n)$
- `sorted(TUPLE)`: $O(n \log n)$ worst case

#### Lists vs Tuples
| Property             | List                | Tuple                                           |
| -------------------- | ------------------- | ----------------------------------------------- |
| Ordered              | Yes                 | Yes                                             |
| Mutable              | Yes                 | No                                              |
| Indexing             | Yes                 | Yes                                             |
| Slicing              | Yes                 | Yes                                             |
| Iteration            | Yes                 | Yes                                             |
| Duplicates           | Allowed             | Allowed                                         |
| Heterogeneous values | Yes                 | Yes                                             |
| Append/remove        | Yes                 | No                                              |
| Concatenation        | Yes                 | Yes                                             |
| Membership           | O(n)                | O(n)                                            |
| Hashable             | No                  | Sometimes<br>When all its elements are hashable |
| Common use           | Dynamic collections | Fixed records                                   |
