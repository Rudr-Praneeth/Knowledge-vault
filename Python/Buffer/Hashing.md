# Hashing
TAGS: #Python 
BUILT-ON: -
ENABLES: - 
PREREQUSITIES: - 

---
# Hashing
Hashing transforms a key into an integer-like value that helps determine where the dictionary should look for that key. 
A ***Hash function*** takes an object and produces a hash value which is an integer value. Conceptually: 
```python
HASH_VALUE = hash(KEY)
```
A dictionary uses this hash value to help locate the key's storage position. An object is hashable if it:
- Has a hash value that remains stable during its lifetime
- Can be compared for equality
- Satisfies the rule that equal objects have equal hash values.
This is why immutable built-in objects are commonly used as dictionary keys. If a mutable object were used as a key and its hash changed after insertion, the dictionary could lose the ability to find the key in the location where it had been stored.
The tuple itself cannot be modified, but its list element is mutable and unhashable. Therefore, tuple hashability depends on the hashability of all its elements.

#### ~={purple}***Important properties***=~:
1. The same object, while it remains in a stable state, must produce a consistent hash value during its lifetime.
2. Objects that compare equal must have equal hash values.
3. Different objects may produce the same hash value.

- $a == b \implies hash(a) == hash(b)$
- $hash(a) == hash(b) \centernot\implies a == b$
  Two unequal objects can have the same hash. This is called a hash collision.

#### ~={purple}***Hash Collisions***=~
A collision occurs when two unequal keys produce the same hash value. Collisions occur because the set of possible objects is enormous, while the hash value space is finite. 
When a candidate location contains an entry with the same hash, the dictionary also checks key equality to determine whether it has found the requested key. If the keys are unequal, the dictionary continues its collision-resolution process to find the correct entry or an available location.
Python's built-in dictionary is implemented using a hash table. CPython uses an open-addressing strategy with probing.
At a high level:
1. Compute the key's hash
2. Identify an initial table position
3. If the position is occupied, inspect another candidate position according to the probing sequence
4. Compare candidate keys when appropriate
5. Continue until the key is found or an available position is found
A hash table aims to distribute entries across its available table positions. If the hash function distributes keys reasonably well and the table maintains sufficient capacity, lookup usually examines only a small number of candidates. This gives average-case O(1) lookup.

#### ~={purple}***Dictionary Operation Time-complexities***=~

| Operation                            | Average-case complexity |
| ------------------------------------ | ----------------------- |
| `data[key]` lookup                   | O(1)                    |
| `data[key] = value` insertion/update | O(1)                    |
| `del data[key]` deletion             | O(1)                    |
| `key in data`                        | O(1)                    |
| `data.get(key)`                      | O(1)                    |
| `data.pop(key)`                      | O(1)                    |
| Iterate over dictionary              | O(n)                    |
| `value in data.values()`             | O(n)                    |
| Copy dictionary                      | O(n)                    |
| Compare dictionaries                 | O(n)                    |

#### ~={purple}***Resizing***=~
A hash table needs enough slots to store entries efficiently.
As a dictionary grows, CPython may allocate a larger table and redistribute entries according to their hashes and the new table layout. This is called resizing.
Most insertions are average-case O(1), but an insertion that triggers a resize can require O(n) work.
This is an example of amortized analysis: although occasional operations are expensive, the average cost over a sequence of insertions remains O(1) per insertion under the usual assumptions.

#### ~={purple}***Hash Randomisation***=~
Python uses hash randomization for certain built-in types, notably strings and bytes, to make it harder for an attacker to deliberately construct inputs that cause excessive hash collisions.
- A string's hash is consistent within a process while the string remains unchanged. It is not generally safe to assume the same string has the same hash across different processes or runs.

#### ~={purple}***User-defined Objects Hashability***=~:
By default, ordinary user-defined objects generally compare by identity unless equality behavior is customized. They are normally hashable by identity as well.
But Python automatically makes a class unhashable when you define `__eq__()` without defining a compatible `__hash__()`.
Never mutate state that contributes to a key's equality or hash while that object is being used as a dictionary key or set element.
```python
class UNHASHABLE_CLASS:
    def __init__(self, user_id):
        self.user_id = user_id

    def __eq__(self, other):
        if not isinstance(other, User):
            return NotImplemented
        return self.user_id == other.user_id
        
class HASHABLE_CLASS:
    def __init__(self, user_id):
        self.user_id = user_id

    def __eq__(self, other):
        if not isinstance(other, User):
            return NotImplemented
        return self.user_id == other.user_id

    def __hash__(self):
        return hash(self.user_id)

OBJECT_1 = UNHASHABLE_CLASS(101)
OBJECT_2 = HASHABLE_CLASS(101)
hash(OBJECT_1) 
# RAISES TypeError SINCE __hash__ NOT DEFINED AND PYTHON SETS User CLASS TO UNHASHABLE

hash(OBJECT_2)
# HASHES SUCCESSFULLY 
```

Working Example:
```python
class User:
    def __init__(self, user_id):
        self.user_id = user_id

    def __eq__(self, other):
        if not isinstance(other, User):
            return NotImplemented
        return self.user_id == other.user_id

    def __hash__(self):
        return hash(self.user_id)
        
u1 = User(101)
u2 = User(101)

print(u1 == u2)                 # True
print(hash(u1) == hash(u2))     # True

users = {u1: "Alex"}
print(users[u2])                # Alex
```

Immutability does not guarantee hashability.
An immutable object may still be unhashable if it lacks a valid __hash__() method.

# END

```python

```