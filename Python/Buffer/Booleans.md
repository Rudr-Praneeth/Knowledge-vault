# Booleans
TAGS: #Python 
BUILT-ON: [[Python Datatypes]]
ENABLES: - 
PREREQUSITIES:  -

---
## Booleans
A **Boolean** is a value representing one of two logical states:
- `True`: the statement or condition is true.
- `False`: the statement or condition is false.
- Booleans are immutable.
- `bool` is a subclass of `int`. `True` behaves as `1` and `False` behaves as `0`.
>~={purple}NOTE=~:
>Because `bool` is a subclass of `int`, arithmetic on Booleans works. It is rarely good style outside of counting, for example `sum(<ITERABLE_OF_BOOLEANS>)` to count how many are `True`.

#### Comparison Operators
Comparison operators are expressions that compare two values and produce a `bool`.
- **`<A> == <B>`**:`True` if the values are equal.
- **`<A> != <B>`**: `True` if the values are not equal.
- **`<A> > <B>`**: `True` if `<A>` is greater than `<B>`.
- **`<A> < <B>`**: `True` if `<A>` is less than `<B>`.
- **`<A> >= <B>`**: `True` if `<A>` is greater than or equal to `<B>`.
- **`<A> <= <B>`**: `True` if `<A>` is less than or equal to `<B>`.

#### Equality Across Types
- Values of unrelated types are usually unequal, not an error: `10 == "10"` is `False`.
- Ordering comparisons (`<`, `>`, `<=`, `>=`) between unrelated types raise `TypeError`: `10 < "10"`.

---
## Logical Operators
Logical operators combine or reverse Boolean conditions.
- **`<A> and <B>`**: `True` only if both are true.
- **`<A> or <B>`**: `True` if at least one is true.
- **`not <A>`**: Reverses the condition.

#### Truth Table
| `a`     | `b`     | `a and b` | `a or b` | `not a` |
| ------- | ------- | --------- | -------- | ------- |
| `True`  | `True`  | `True`    | `True`   | `False` |
| `True`  | `False` | `False`   | `True`   | `False` |
| `False` | `True`  | `False`   | `True`   | `True`  |
| `False` | `False` | `False`   | `False`  | `True`  |
#### Precedence
From highest to lowest: comparisons, `not`, `and`, `or`. Use parentheses to make the intent explicit.

#### Short-Circuit Evaluation
- `<A> and <B>`: if `<A>` is false, `<B>` is not evaluated.
- `<A> or <B>`: if `<A>` is true, `<B>` is not evaluated.

#### Logical vs Bitwise
- `and`, `or`, `not` are logical operators.
- `&`, `|`, `~` are bitwise operators. They are not substitutes for the logical operators.

#### Boolean Conversion
- **`bool(<OBJECT>)`**: Converts an object to `True` or `False` using its truth value.
- The built-in objects that evaluate to `False` are: `False`, `None`, numeric zeros (`0`, `0.0`), and empty containers (`""`, `[]`, `()`, `{}`, `set()`).
- Almost everything else evaluates to `True`.

# END
---
#### FOOTNOTES