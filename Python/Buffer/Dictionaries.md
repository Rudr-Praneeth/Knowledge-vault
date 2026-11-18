# Dictionaries
TAGS: #Python 
BUILT-ON: [[Data Structures]]
ENABLES: - 
PREREQUSITIES: [[Hashing]]

---
# Dictionaries
A dictionary is a built-in Python data structure which is an insertion-ordered, mutable collection that stores a mapping associating unique keys with values. A dictionary is used to look up, insert, modify and delete data by key, in average constant time.

#### ~={purple}***Characteristics of Dictionaries***=~
- ***Collection of Object References***: Stores references to key objects and value objects.
- ***Ordered***: Dictionaries preserve insertion order (guaranteed since Python 3.7).
- ***Mutable***: Key-value pairs can be added, modified and removed after creation.
- ***Non-Indexed***: Values are accessed through keys, not positions.
- ***Unique Keys***: Inserting an existing key replaces its value instead of adding a duplicate.
- ***Duplicate-Friendly Values***: Different keys can reference equal values.
- ***Heterogeneous Elements***: Keys and values can have different types (keys must be hashable).

#### ~={purple}***Creation of Dictionaries***=~
1. ***Using Curly Brackets `{}`***:
   ```python
   DICTIONARY = {}
   DICTIONARY = {KEY: VALUE, ...}
   ```
2. ***Using `dict()` Constructor***:
   ```python
   DICTIONARY = dict()
   DICTIONARY = dict(KEY=VALUE, ...)  # KEYS MUST BE VALID IDENTIFIERS (STRINGS)
   DICTIONARY = dict([(KEY, VALUE), (KEY, VALUE), ...])
   DICTIONARY = dict(OTHER_DICTIONARY)  # SHALLOW COPY
   ```
3. ***Using `fromkeys()` Method***:
   ```python
   DICTIONARY = dict.fromkeys([KEY, KEY, ...], VALUE)
   # EVERY KEY REFERENCES THE SAME VALUE OBJECT
   # VALUE DEFAULTS TO None
   ```
4. ***Using Dictionary Comprehension***:
   ```python
   DICTIONARY = {KEY: VALUE for ITEM in ITERABLE if CONDITION}
   ```

#### ~={purple}***Accessing Dictionary Elements***=~
- ***Square-bracket access***: Raises `KeyError` for a missing key.
- ***Using `get()` Method***: Returns `None` (or the fallback) for a missing key; never raises.
  ```python
  VALUE = DICTIONARY[KEY]              # RAISES KeyError IF KEY MISSING
  VALUE = DICTIONARY.get(KEY)          # None IF KEY MISSING
  VALUE = DICTIONARY.get(KEY, FALLBACK)  # FALLBACK IF KEY MISSING
  ```
- `get()` does not insert the key. `setdefault()` does.

#### ~={purple}***Key-Values Property***=~
| Aspect      | Keys                                                   | Values       |
| ----------- | ------------------------------------------------------ | ------------ |
| Hashability | Required                                               | Not required |
| Unique      | Yes                                                    | No           |
| Mutability  | Not if mutation affects hashability/equality           | Yes          |
| Valid types | `int`, `str`, `tuple` (of hashables), `frozenset`, ... | Any object   |
| Invalid     | `list`, `dict`, `set` (unhashable)                     | -            |

If two objects compare equal, they must have equal hash values. A dictionary treats equal keys as the same key (`1`, `1.0` and `True` are the same key).

#### ~={purple}***Membership Testing***=~
For dictionaries, `in` checks keys, not values.
```python
BOOLEAN = KEY in DICTIONARY
BOOLEAN = VALUE in DICTIONARY.values()
BOOLEAN = (KEY, VALUE) in DICTIONARY.items()
```
Average-case complexity:
- Key membership: O(1)
- Value membership: O(n)
- Key-value pair membership: O(1) (the `items()` view looks up the key, then compares the value)

#### ~={purple}***Equality Testing***=~
Dictionaries preserve insertion order during iteration, but dictionary equality does not depend on that order. Two dictionaries are equal if they contain the same key-value associations. Ordering comparisons (`<`, `>`, `<=`, `>=`) are not supported and raise `TypeError`

#### ~={purple}***Adding, Updating and Deleting Entries***=~
The syntax `DICTIONARY[KEY] = VALUE` handles both operations.
- If the key exists, its value is replaced.
- If it does not exist, a new entry is inserted at the end.

***DICTIONARY UPDATION***:
- Multiple entries can be updated using `update()`. Existing keys are updated; new keys are inserted.
- A value can be set and retrieved in the same step using `setdefault()`. It returns the value if the key exists. Otherwise, it inserts the key with the default value and returns that value.
```python
DICTIONARY.update({KEY: VALUE, KEY: VALUE})
DICTIONARY.update(OTHER_DICTIONARY)
DICTIONARY.update(KEY=VALUE)
DICTIONARY.update([(KEY, VALUE), (KEY, VALUE)])

VALUE = DICTIONARY.setdefault(KEY, DEFAULT_VALUE)
# INSERTS KEY WITH DEFAULT IF ABSENT; RETURNS CURRENT VALUE EITHER WAY
```

***DICTIONARY DELETION***:
- `del` removes an entry. Raises `KeyError` if the key does not exist.
- `pop()` removes the key and returns its value. Without a default it raises `KeyError`; with a default it returns that default.
- `popitem()` removes and returns the most recently inserted pair (LIFO). Raises `KeyError` if the dictionary is empty.
- `clear()` removes all entries while keeping the dictionary object itself.
```python
del DICTIONARY[KEY]

VALUE = DICTIONARY.pop(KEY)                 # RAISES KeyError IF KEY MISSING
VALUE = DICTIONARY.pop(KEY, DEFAULT_VALUE)  # DEFAULT_VALUE IF KEY ABSENT

(KEY, VALUE) = DICTIONARY.popitem()         # RAISES KeyError IF DICTIONARY EMPTY

DICTIONARY.clear()
```

#### ~={purple}***Dictionary Views***=~
`keys()`, `values()` and `items()` return view objects (`dict_keys`, `dict_values`, `dict_items`), not lists.
- Views are dynamic: they reflect later changes to the dictionary.
- Views are iterable, support `len()`, `in` and `reversed()`.
- `keys()` and `items()` are set-like and support `&`, `|`, `-`, `^`. `values()` is not set-like.
```python
DICTIONARY = {KEY_1: VALUE_1, KEY_2: VALUE_2}
KEYS = DICTIONARY.keys()      # dict_keys([KEY_1, KEY_2])
VALUES = DICTIONARY.values()  # dict_values([VALUE_1, VALUE_2])
ITEMS = DICTIONARY.items()    # dict_items([(KEY_1, VALUE_1), (KEY_2, VALUE_2)])

DICTIONARY[KEY_3] = VALUE_3

print(KEYS)    # dict_keys([KEY_1, KEY_2, KEY_3])
print(VALUES)  # dict_values([VALUE_1, VALUE_2, VALUE_3])
print(ITEMS)   # dict_items([(KEY_1, VALUE_1), (KEY_2, VALUE_2), (KEY_3, VALUE_3)])

SNAPSHOT = list(DICTIONARY.keys())  # STATIC COPY, DOES NOT UPDATE
```

#### ~={purple}***Iterating over Dictionaries***=~
- A dictionary is iterable. Default iteration produces keys.
```python
for KEY in DICTIONARY:
	WORK()
for KEY in DICTIONARY.keys():
	WORK()
for VALUE in DICTIONARY.values():
	WORK()
for KEY, VALUE in DICTIONARY.items():
	WORK()
for KEY in reversed(DICTIONARY):   # PYTHON 3.8+
	WORK()
```
Do not add or remove keys while iterating a dictionary. It raises `RuntimeError: dictionary changed size during iteration`. Changing the value of an existing key is safe. For structural changes, iterate over a snapshot (`list(DICTIONARY)`) or build a new dictionary.
```python
# WRONG METHOD
for KEY in DICTIONARY:
	if KEY == "KEY":
		del DICTIONARY["KEY"]

# CORRECT APPROACH: SNAPSHOT
for KEY in list(DICTIONARY):
	if KEY == "KEY":
		del DICTIONARY["KEY"]

# CORRECT APPROACH: NEW DICTIONARY
FILTERED = {KEY: VALUE for KEY, VALUE in DICTIONARY.items() if KEY != "KEY"}
```

#### ~={purple}***Merging Dictionaries***=~
- ***Using `update()` method***: in place.
- ***Using `|` Union operator***: new dictionary (Python 3.9+).
- ***Using `|=` In-place Union***: in place (Python 3.9+).
- ***Using `{**D1, **D2}` unpacking***: new dictionary.
- On key conflict, the right-hand (later) value wins.
```python
DICTIONARY_1.update(DICTIONARY_2)
DICTIONARY = DICTIONARY_1 | DICTIONARY_2
DICTIONARY_1 |= DICTIONARY_2
DICTIONARY = {**DICTIONARY_1, **DICTIONARY_2}
```

#### ~={purple}***Dictionary Operations***=~

| Operation                                    | Use Case                                                                  | Argument Types                                              | Return Type                          |
| -------------------------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------- | ------------------------------------ |
| ~={cyan}**Dictionary Creation**=~            |                                                                           |                                                             |                                      |
| `fromkeys(ITERABLE, *VALUE)`                 | Class method: create a dictionary from keys, all sharing one value        | `ITERABLE: Iterable`, `VALUE: Any (optional, default None)` | `Dictionary`                         |
| ~={cyan}**Element Access**=~                 |                                                                           |                                                             |                                      |
| `get(KEY, *DEFAULT)`                         | Return value for key; `DEFAULT` (or `None`) if missing; never raises      | `KEY: Hashable`, `DEFAULT: Any (optional)`                  | `Value Type` or `Default`            |
| `setdefault(KEY, *DEFAULT)`                  | Return value if key exists; else insert key with default and return it    | `KEY: Hashable`, `DEFAULT: Any (optional, default None)`    | `Value Type` or `Default`            |
| ~={cyan}**Element Insertion / Update**=~     |                                                                           |                                                             |                                      |
| `update(OTHER)`                              | Insert or overwrite entries from a mapping or iterable of pairs           | `OTHER: Mapping or Iterable of pairs`, or keyword arguments | `None`                               |
| ~={cyan}**Element Removal**=~                |                                                                           |                                                             |                                      |
| `pop(KEY, *DEFAULT)`                         | Remove key and return its value; `KeyError` if missing without default    | `KEY: Hashable`, `DEFAULT: Any (optional)`                  | `Value Type` or `Default`            |
| `popitem()`                                  | Remove and return the last inserted pair (LIFO); `KeyError` if empty      | None                                                        | `Tuple (KEY, VALUE)`                 |
| `clear()`                                    | Remove all entries                                                        | None                                                        | `None`                               |
| ~={cyan}**Dictionary Views**=~               |                                                                           |                                                             |                                      |
| `keys()`                                     | Dynamic view of keys                                                      | None                                                        | `dict_keys`                          |
| `values()`                                   | Dynamic view of values                                                    | None                                                        | `dict_values`                        |
| `items()`                                    | Dynamic view of `(KEY, VALUE)` pairs                                      | None                                                        | `dict_items`                         |
| ~={cyan}**Collection Copy**=~                |                                                                           |                                                             |                                      |
| `copy()`                                     | Create a shallow copy of the dictionary                                   | None                                                        | `Dictionary`                         |
| ~={cyan}**Additional Dictionary Operations**=~ |                                                                         |                                                             |                                      |
| `__getitem__(KEY)`                           | Retrieve a value using `DICTIONARY[KEY]`; `KeyError` if missing           | `KEY: Hashable`                                             | `Value Type`                         |
| `__setitem__(KEY, VALUE)`                    | Insert or update using `DICTIONARY[KEY] = VALUE`                          | `KEY: Hashable`, `VALUE: Any`                               | `None`                               |
| `__delitem__(KEY)`                           | Delete an entry using `del`; `KeyError` if missing                        | `KEY: Hashable`                                             | `None`                               |
| `__contains__(KEY)`                          | Check key membership using `in`                                           | `KEY: Hashable`                                             | `Boolean`                            |
| `__iter__()`                                 | Return an iterator over the keys                                          | None                                                        | `Iterator`                           |
| `__reversed__()`                             | Return a reverse iterator over keys (3.8+)                                | None                                                        | `Iterator`                           |
| `__len__()`                                  | Return the number of entries using `len()`                                | None                                                        | `Integer`                            |
| `__or__(OTHER)`                              | Merge into a new dictionary using `\|` (3.9+)                             | `OTHER: Dictionary`                                         | `Dictionary`                         |
| `__ror__(OTHER)`                             | Reflected `\|`, used when the left operand is not a dictionary (3.9+)     | `OTHER: Dictionary`                                         | `Dictionary`                         |
| `__ior__(OTHER)`                             | Merge in place using `\|=`; accepts any mapping or iterable of pairs (3.9+) | `OTHER: Mapping or Iterable of pairs`                     | `Dictionary` (same dictionary object)|
| `__eq__(OTHER)`                              | Compare dictionaries for equality using `==` (order-independent)          | `OTHER: Any`                                                | `Boolean`                            |
| `__ne__(OTHER)`                              | Compare dictionaries for inequality using `!=`                            | `OTHER: Any`                                                | `Boolean`                            |
| `__missing__(KEY)`                           | Called by `__getitem__` on missing key; only exists in subclasses (e.g. `defaultdict`) | `KEY: Hashable`                                | `Value Type`                         |
| `__repr__()`                                 | Return the official string representation                                 | None                                                        | `String`                             |
| `__str__()`                                  | Return the string representation                                          | None                                                        | `String`                             |
| `__sizeof__()`                               | Return the shallow size of the dictionary object in bytes                 | None                                                        | `Integer`                            |

#### Notes: 
- `Hashable` means an object with a stable hash value, such as `int`, `str`, or a `tuple` of hashables.
- `Mapping` means an object with key-value associations, such as another dictionary.
- Dictionaries do not define `<`, `<=`, `>`, `>=`. They raise `TypeError`.
- Dictionaries have no `sort()`. Use `sorted(DICTIONARY.items(), key=...)` and rebuild with `dict(...)`.
- The dunder methods (`__method__`) are special methods, usually invoked indirectly by operators or built-in functions. They are included for completeness but are not normally called directly.
- `__sizeof__()` reports the object's shallow memory size, not the total memory occupied by nested keys and values.

#### ~={purple}*Dictionary Time Complexities*=~
- `KEY in DICTIONARY`: $\Theta(1)$ average, $O(n)$ worst case (hash collisions)
- `DICTIONARY[KEY]` / `get(KEY)`: $\Theta(1)$ average, $O(n)$ worst case
- `DICTIONARY[KEY] = VALUE`: $\Theta(1)$ amortized average
- `del DICTIONARY[KEY]` / `pop(KEY)`: $\Theta(1)$ average
- `popitem()`: $\Theta(1)$
- `setdefault(KEY, DEFAULT)`: $\Theta(1)$ average
- `VALUE in DICTIONARY.values()`: $\Theta(n)$
- `(KEY, VALUE) in DICTIONARY.items()`: $\Theta(1)$ average
- `update(OTHER)`: $\Theta(m)$, where $m$ = size of `OTHER`
- `copy()`: $\Theta(n)$
- `DICTIONARY_1 | DICTIONARY_2`: $\Theta(n + m)$
- `keys()`, `values()`, `items()`: $\Theta(1)$ (views); iterating them is $\Theta(n)$
- `len(DICTIONARY)`: $\Theta(1)$
