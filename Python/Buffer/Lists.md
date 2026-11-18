# Lists
TAGS: #Python 
BUILT-ON: [[Data Structures]]
ENABLES: - 
PREREQUSITIES: - 

---
# Lists
A list is a built-in Python data structure which is an ordered, mutable collection of objects. A list is used to store related data and treat it as a single object, access it, modify it and pass it to functions, etc.
#### ~={purple}***Characteristics of Lists***=~
- ***Collection of Objects***: References of multiple objects stored under a single name.
- ***Duplicate-Friendly***: Lists allow insertion of duplicate elements.
- ***Heterogeneous Elements***: Lists can store objects of different data types.
- ***Mutable***: Collection can be modified after creation.
- ***Ordered***: Elements in the list are positioned and preserve their relative order.
- ***Indexed***: Elements in a list can be accessed using indices. A list uses zero-based indexing.
  Attempting to access an index outside the valid range raises `IndexError`.

#### ~={purple}***Creation of Lists***=~
Python allows multiple ways in which lists can be created. They are as follows:
1. ***Using Square Brackets***:
   ```python
   LIST = [*ELEMENT...]
   ```
2. **Using `list` Constructor**:
   ```python
   LIST = list(ITERABLE)
   
   ITERABLE = (ELEMENT, ELEMENT, ELEMENT) | STRING
   ```

#### ~={purple}***Accessing List Elements***=~
1. ***Zero-based Indexing***: A list uses zero-based indexing: the first element has index `0`. 
   Attempting to access an index outside the valid range raises `IndexError`.
   `ELEMENT = LIST[INDEX]`
2. ***Negative indexing***: Negative indexing access list elements from the end
   Negative indexing is useful when the position of interest is relative to the end, such as the most recent item.
   `ELEMENT = LIST[-INDEX]`
3. ***Slice Indexing***: Slice indexing retrieves a section of a list by specifying the starting index, stopping index, and step size. It returns a new list containing the selected elements.
   `SUB_LIST = LIST[START: STOP: STEP]`
   - `START`: Index to begin slicing from (inclusive; defaults to the beginning).
   - `STOP`: Index to stop slicing at (exclusive; defaults to the end).
   - `STEP`: Interval between selected elements (defaults to `1`; can be negative to traverse backwards).

#### ~={purple}***List Operations***=~

| Operation                                | Use Case                                                                | Argument Types                                                        | Return Type               |
| ---------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------- | ------------------------- |
| ~={cyan}**Element Insertion**=~          |                                                                         |                                                                       |                           |
| `append(ELEMENT)`                        | Add one element at the end                                              | `ELEMENT: Any`                                                        | `None`                    |
| `extend(ITERABLE)`                       | Add elements from an iterable                                           | `ITERABLE: Iterable`                                                  | `None`                    |
| `insert(INDEX, ELEMENT)`                 | Insert before index `INDEX`                                             | `INDEX: Integer`, `ELEMENT: Any`                                      | `None`                    |
| ~={cyan}**Element Removal**=~            |                                                                         |                                                                       |                           |
| `remove(VALUE)`                          | Remove the first matching value; raises `ValueError` if not found       | `VALUE: Any`                                                          | `None`                    |
| `pop(*INDEX)`                            | Remove and return the element at `INDEX`; defaults to the last element  | `INDEX: Integer (optional)`                                           | `Element Type`            |
| `clear()`                                | Remove all elements                                                     | None                                                                  | `None`                    |
| ~={cyan}**Element Position Search**=~    |                                                                         |                                                                       |                           |
| `index(VALUE, *START, *STOP)`            | Find the index of the first matching value within the optional range    | `VALUE: Any`, `START: Integer (optional)`, `STOP: Integer (optional)` | `Integer`                 |
| `count(VALUE)`                           | Count occurrences of a value                                            | `VALUE: Any`                                                          | `Integer`                 |
| ~={cyan}**Element Arrangement**=~        |                                                                         |                                                                       |                           |
| `sort(*KEY, *REVERSE)`                   | Sort the list in place using an optional key function and reverse order | `KEY: Callable (optional)`, `REVERSE: Boolean (optional)`             | `None`                    |
| `reverse()`                              | Reverse the list in place                                               | None                                                                  | `None`                    |
| ~={cyan}**Collection Copy**=~            |                                                                         |                                                                       |                           |
| `copy()`                                 | Create a shallow copy of the list                                       | None                                                                  | `List`                    |
| ~={cyan}**Additional List Operations**=~ |                                                                         |                                                                       |                           |
| `__add__(OTHER)`                         | Concatenate two lists using the `+` operator                            | `OTHER: List`                                                         | `List`                    |
| `__iadd__(ITERABLE)`                     | Extend the list using the `+=` operator                                 | `ITERABLE: Iterable`                                                  | `List` (same list object) |
| `__mul__(COUNT)`                         | Repeat the list using the `*` operator                                  | `COUNT: Integer`                                                      | `List`                    |
| `__rmul__(COUNT)`                        | Repeat the list when the integer is on the left, e.g. `3 * items`       | `COUNT: Integer`                                                      | `List`                    |
| `__imul__(COUNT)`                        | Repeat the list in place using `*=`                                     | `COUNT: Integer`                                                      | `List` (same list object) |
| `__getitem__(INDEX_OR_SLICE)`            | Retrieve an element or a slice using indexing                           | `INDEX_OR_SLICE: Integer or Slice`                                    | `Element Type` or `List`  |
| `__setitem__(INDEX_OR_SLICE, VALUE)`     | Assign a value or iterable to an index or slice                         | `INDEX_OR_SLICE: Integer or Slice`, `VALUE: Any or Iterable`          | `None`                    |
| `__delitem__(INDEX_OR_SLICE)`            | Delete an element or slice using `del`                                  | `INDEX_OR_SLICE: Integer or Slice`                                    | `None`                    |
| `__contains__(VALUE)`                    | Check membership using `in`                                             | `VALUE: Any`                                                          | `Boolean`                 |
| `__iter__()`                             | Return an iterator over the list                                        | None                                                                  | `Iterator`                |
| `__reversed__()`                         | Return a reverse iterator                                               | None                                                                  | `Iterator`                |
| `__len__()`                              | Return the number of elements using `len()`                             | None                                                                  | `Integer`                 |
| `__eq__(OTHER)`                          | Compare lists for equality using `==`                                   | `OTHER: Any`                                                          | `Boolean`                 |
| `__ne__(OTHER)`                          | Compare lists for inequality using `!=`                                 | `OTHER: Any`                                                          | `Boolean`                 |
| `__lt__(OTHER)`                          | Compare lists using `<` lexicographically                               | `OTHER: List`                                                         | `Boolean`                 |
| `__le__(OTHER)`                          | Compare lists using `<=` lexicographically                              | `OTHER: List`                                                         | `Boolean`                 |
| `__gt__(OTHER)`                          | Compare lists using `>` lexicographically                               | `OTHER: List`                                                         | `Boolean`                 |
| `__ge__(OTHER)`                          | Compare lists using `>=` lexicographically                              | `OTHER: List`                                                         | `Boolean`                 |
| `__repr__()`                             | Return the official string representation of the list                   | None                                                                  | `String`                  |
| `__str__()`                              | Return the string representation of the list                            | None                                                                  | `String`                  |
| `__sizeof__()`                           | Return the shallow size of the list object in bytes                     | None                                                                  | `Integer`                 |

Notes: 
- `Iterable` means an object that can provide its elements one at a time, such as a list, tuple, string, or generator.
- `KEY` must be a callable that accepts a list element and returns a value used for sorting.
- The dunder methods (`__method__`) are special methods, usually invoked indirectly by operators or built-in functions. They are included for completeness but are not normally called directly.
- `__sizeof__()` reports the object's shallow memory size, not the total memory occupied by all nested elements.

>`del` statement removes an element, a slice, or a variable binding.
>`del` statement works similar to pop but doesn't return the element.
```python
LIST = [I1, I2, I3]
del LIST[1]
# LIST[I1, I3]
```

#### ~={purple}***List Iterations***=~
**Direct Iteration**:
```python
for ELEMENT in LIST:
	WORK()
```
**Iterating with Indices**
```python
for INDEX in RANGE(LEN(LIST)):
	WORK()

for INDEX, ELEMENT in enumerate(LIST):
	WORK()
```

#### ~={purple}*List Time Complexities*=~
- `ELEMENT in LIST`: $\Theta(n)$ worst case
- `LIST.index(ELEMENT)`: $\Theta(n)$ worst case
- `LIST.count(ELEMENT)`: $\Theta(n)$
- `LIST.append(ELEMENT)`: $\Theta(1)$ Amortized
- `LIST.pop()` *at the end*: $\Theta(1)$
- `LIST.pop(0)`: $\Theta(n)$
- `LIST.insert(INDEX, ELEMENT)`: $\Theta(n)$
- `LIST.remove(ELEMENT)`: $\Theta(n)$ worst case
- `LIST.copy()`: $\Theta(n)$
- `LIST.reverse()`: $\Theta(n)$
- `LIST.sort()`: $\Theta(n log n)$ worst case
- `min(LIST)` or `max(LIST)`: $\Theta(n)$
- `LIST_1 + LIST_2`: $\Theta(n + m)$

