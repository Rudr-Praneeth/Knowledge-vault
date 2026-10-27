# Strings
TAGS: #Python 
BUILT-ON: [[Python Datatypes]]
ENABLES: - 
PREREQUSITIES:  -

---
## Strings
Strings are ***immutable*** in Python.
A **string** is a Python object representing text. Strings can contain:
- Letters
- Numbers
- Spaces
- Punctuations
- Symbols
- Unicode characters

#### Escape Sequences
An **escape sequence** is a special character representation beginning with `\`.
- New line: `\n`
- Tab Space: `\t`
- Backslash: `\\`
- Single Quote: `\'`
- Double Quote: `\"`

## String Operations
#### Case Conversion
- **`<STRING>.lower()`**  
    Returns a copy with all cased characters converted to lowercase.
- **`<STRING>.upper()`**  
    Returns a copy with all cased characters converted to uppercase.
- **`<STRING>.casefold()`**  
    Returns a copy suitable for caseless comparison. It is more aggressive than `lower()`; for example, `ß` becomes `ss`.
- **`<STRING>.capitalize()`**  
    Returns a copy with the first character in uppercase and all remaining characters in lowercase.
- **`<STRING>.title()`**  
    Returns a copy with the first letter of each word in uppercase and all other letters in lowercase. Word boundaries are determined by non-letter characters, so apostrophes may yield unexpected results.
- **`<STRING>.swapcase()`**  
    Returns a copy in which uppercase characters become lowercase and lowercase characters become uppercase.

#### Searching and Counting
- **`<STRING>.find(<SUB_STRING>, <START>, <END>)`**  
    Returns the lowest index at which `<SUB_STRING>` is found, or `-1` if it is absent.
- **`<STRING>.rfind(<SUB_STRING>, <START>, <END>)`**  
    Returns the highest index at which `<SUB_STRING>` is found, or `-1` if it is absent.
- **`<STRING>.index(<SUB_STRING>, <START>, <END>)`**  
    Equivalent to `find()`, but raises `ValueError` if `<SUB_STRING>` is absent.
- **`<STRING>.rindex(<SUB_STRING>, <START>, <END>)`**  
    Equivalent to `rfind()`, but raises `ValueError` if `<SUB_STRING>` is absent.
- **`<STRING>.count(<SUB_STRING>, <START>, <END>)`**  
    Returns the number of non-overlapping occurrences of `<SUB_STRING>`.
- **`<SUB_STRING> in <STRING>`**  
    Membership operator (not a method). Returns `True` if `<SUB_STRING>` occurs in `<STRING>`. Prefer it over `find()` when only presence matters.

#### Prefix and Suffix Testing
- **`<STRING>.startswith(<PREFIX>, <START>, <END>)`**  
    Returns `True` if the string begins with `<PREFIX>`. `<PREFIX>` may be a tuple of alternatives.
- **`<STRING>.endswith(<SUFFIX>, <START>, <END>)`**  
    Returns `True` if the string ends with `<SUFFIX>`. `<SUFFIX>` may be a tuple of alternatives.

#### Splitting and Partitioning
- **`<STRING>.split(<SEP>, <MAXSPLIT>)`**  
    Returns a list of substrings divided at `<SEP>`. If `<SEP>` is omitted, the string is split on runs of whitespace and empty strings are discarded. `<MAXSPLIT>` limits the number of splits.
- **`<STRING>.rsplit(<SEP>, <MAXSPLIT>)`**  
    Equivalent to `split()`, but splits are counted from the right.
- **`<STRING>.splitlines(<KEEPENDS>)`**  
    Returns a list of lines, split at line boundaries (`\n`, `\r\n`, `\r`, and others). Line endings are retained if `<KEEPENDS>` is `True`.
- **`<STRING>.partition(<SEP>)`**  
    Splits at the first occurrence of `<SEP>` and returns a 3-tuple: `(<BEFORE>, <SEP>, <AFTER>)`. If `<SEP>` is absent, returns `(<STRING>, "", "")`.
- **`<STRING>.rpartition(<SEP>)`**  
    Splits at the last occurrence of `<SEP>`. If `<SEP>` is absent, returns `("", "", <STRING>)

#### Joining
- **`<SEP>.join(<ITERABLE>)`**  
    Returns a string in which the elements of `<ITERABLE>` are concatenated, with `<SEP>` placed between them. All elements must be strings; otherwise `TypeError` is raised.

#### Replacement and Translation
- **`<STRING>.replace(<OLD>, <NEW>, <COUNT>)`**  
    Returns a copy with occurrences of `<OLD>` replaced by `<NEW>`. If `<COUNT>` is given, only the first `<COUNT>` occurrences are replaced.
- **`str.maketrans(<X>, <Y>, <Z>)`**  
    Static method that builds a translation table for `translate()`. With one argument, `<X>` is a dictionary mapping characters (or ordinals) to replacements. With two arguments, `<X>` and `<Y>` are equal-length strings mapped position by position. The optional `<Z>` lists characters to delete.
- **`<STRING>.translate(<TABLE>)`**  
    Returns a copy in which each character is mapped through `<TABLE>`. Characters mapped to `None` are deleted.

#### Character Class Validation
All methods in this group return `False` for an empty string.
- **`<STRING>.isalpha()`**  
    `True` if all characters are alphabetic.
- **`<STRING>.isdigit()`**  
    `True` if all characters are digits, including superscripts such as `²`.
- **`<STRING>.isdecimal()`**  
    `True` if all characters are decimal digits (those usable to form base-10 numbers). It is the strictest numeric test.
- **`<STRING>.isnumeric()`**  
    `True` if all characters have a numeric property, including fractions such as `½` and numerals from other scripts. It is the broadest numeric test.
- **`<STRING>.isalnum()`**  
    `True` if all characters are alphabetic or numeric.
- **`<STRING>.isspace()`**  
    `True` if all characters are whitespace.
- **`<STRING>.isascii()`**  
    `True` if all characters are in the ASCII range (code points 0 to 127). Unlike the others, it returns `True` for an empty string.
- **`<STRING>.isprintable()`**  
    `True` if all characters are printable. Whitespace other than the ordinary space is non-printable. It returns `True` for an empty string.
- **`<STRING>.isidentifier()`**  
    `True` if the string is a valid Python identifier. Keywords such as `class` also return `True`; use `keyword.iskeyword()` to exclude them.

#### Case Validation
- **`<STRING>.islower()`**  
    `True` if the string contains at least one cased character and all cased characters are lowercase.
- **`<STRING>.isupper()`**  
    `True` if the string contains at least one cased character and all cased characters are uppercase.
- **`<STRING>.istitle()`**  
    `True` if the string is title-cased: uppercase characters follow only uncased characters, and lowercase characters follow only cased ones.

#### Formatting
- **`<STRING>.format(<ARGS>, <KWARGS>)`**  
    Returns a copy in which replacement fields delimited by `{}` are substituted with the given arguments, for example `"{0}, {name}"`.
- **`<STRING>.format_map(<MAPPING>)`**  
    Equivalent to `format()`, but takes a single mapping directly without copying it into a new dictionary.
- **`<STRING> % <VALUES>`**  
    Printf-style formatting operator (not a method). Supports specifiers such as `%s`, `%d`, and `%f`.

#### Whitespace and Boundary Trimming
- **`<STRING>.strip(<CHARS>)`**  
    Returns a copy with leading and trailing characters removed. If `<CHARS>` is omitted, whitespace is removed. `<CHARS>` is treated as a set of characters, not a sequence.
- **`<STRING>.lstrip(<CHARS>)`**  
    Returns a copy with leading characters removed.
- **`<STRING>.rstrip(<CHARS>)`**  
    Returns a copy with trailing characters removed.
- **`<STRING>.removeprefix(<PREFIX>)`**  
    Returns a copy with `<PREFIX>` removed from the start if present; otherwise returns the original string unchanged. Unlike `lstrip()`, it removes the exact sequence once.
- **`<STRING>.removesuffix(<SUFFIX>)`**  
    Returns a copy with `<SUFFIX>` removed from the end if present; otherwise returns the original string unchanged.

#### Alignment and Padding
- **`<STRING>.center(<WIDTH>, <FILL_CHAR>)`**  
    Returns a copy centered within a field of length `<WIDTH>`, padded with `<FILL_CHAR>` (default: space).
- **`<STRING>.ljust(<WIDTH>, <FILL_CHAR>)`**  
    Returns a copy left-aligned within a field of length `<WIDTH>`.
- **`<STRING>.rjust(<WIDTH>, <FILL_CHAR>)`**  
    Returns a copy right-aligned within a field of length `<WIDTH>`.



---
## Formatted Strings: f-strings
Formatted Strings or f-strings are string literals prefixed with `f` or `F` that embed expressions inside `{}`. Each expression is evaluated at runtime and its result is inserted into the string.
```py
FORMATTED_STRING = f"<TEXT> {<EXPRESSION>} <TEXT>"
```
- Any valid Python expression may appear inside `{}`: variables, arithmetic, function calls, method calls, indexing.
- Literal braces are written by doubling them: `{{` and `}}`.
- An f-string is evaluated once at the point of execution and produces an ordinary `str`.

#### Format Specification
A format specification follows a colon inside the braces.
```py
f"{<EXPRESSION>:<FORMAT_SPEC>}"
```
The general layout of `<FORMAT_SPEC>` is:
```
[[<FILL>]<ALIGN>] 
Alignment, with an optional fill character in front. 
<ALIGN> is one of <, >, ^, =. 
<FILL> can only be given if <ALIGN> is given right after it.

[<SIGN>]
How the sign is shown for numbers: `+`, `-`, or a space.
 
[#] 
“Alternate form”. For integers, adds the `0b`, `0o`, `0x` prefix.

[0] 
Zero-pads numbers to the width.

[<WIDTH>] 
Minimum total width of the field, as an integer.

[<GROUPING>] 
Thousands separator: , or _.

[.<PRECISION>] 
A dot followed by an integer. Digits after the decimal point for floats, or maximum characters for strings.

[<TYPE>]
The presentation type: f, e, %, d, b, x, s, and so on.

```
All components are optional, but they must appear in this order.

#### Conversion Flags
A conversion flag follows `!` and is applied before formatting.
- **`{<EXPRESSION>!s}`**  
    Applies `str()` to the value.
- **`{<EXPRESSION>!r}`**  
    Applies `repr()` to the value. Useful for exposing quotes and escape characters.
- **`{<EXPRESSION>!a}`**  
    Applies `ascii()` to the value, escaping non-ASCII characters.

#### Alignment, Fill and Width
- **`{<EXPRESSION>:<WIDTH>}`**  
    Reserves a field of minimum length `<WIDTH>`. Strings align left by default; numbers align right.
- **`{<EXPRESSION>:<}`**, **`{<EXPRESSION>:>}`**, **`{<EXPRESSION>:^}`**  
    Align left, right, and centre respectively within `<WIDTH>`.
- **`{<EXPRESSION>:<FILL><ALIGN><WIDTH>}`**  
    Pads the field with `<FILL>` instead of spaces. `<FILL>` is a single character placed before `<ALIGN>`.
- **`{<EXPRESSION>:=<WIDTH>}`**  
    Numeric only. Places padding between the sign and the digits.
```py
f"{<STRING>:*^20}"   # centred in 20 characters, padded with *
f"{<NUMBER>:08}"     # zero-padded to width 8
```

#### Numeric Formatting
- **`{<NUMBER>:.<PRECISION>f}`**  
    Fixed-point notation with `<PRECISION>` digits after the decimal point. The value is rounded.
- **`{<NUMBER>:.<PRECISION>e}`**  
    Scientific notation.
- **`{<NUMBER>:.<PRECISION>%}`**  
    Multiplies by 100, formats with `<PRECISION>` decimals, and appends `%`.
- **`{<NUMBER>:.<PRECISION>g}`**  
    General format. Chooses fixed-point or scientific based on magnitude.
- **`{<NUMBER>:,}`** and **`{<NUMBER>:_}`**  
    Inserts `,` or `_` as a thousands separator.
- **`{<NUMBER>:+}`**  
    Always displays the sign. A space (`{<NUMBER>: }`) displays a leading space for positive numbers; `-` (default) shows the sign for negatives only.
- **`{<STRING>:.<PRECISION>}`**  
    When applied to a string, truncates it to `<PRECISION>` characters.

#### Integer Type Codes
- **`d`**: decimal integer.
- **`b`**: binary.
- **`o`**: octal.
- **`x`** / **`X`**: hexadecimal in lowercase / uppercase.
- **`c`**: the character with the given Unicode code point.
- **`#`** flag: adds the prefix `0b`, `0o`, or `0x` for `b`, `o`, `x` respectively.
```py
f"{<NUMBER>:#x}"     # hexadecimal with 0x prefix
f"{<NUMBER>:08b}"    # binary, zero-padded to width 8
```

#### Self-Documenting Expressions
- **`{<EXPRESSION>=}`**  
    Produces the expression text, an `=`, and the `repr()` of its value. Useful for debugging.
- A format specification may follow: `{<EXPRESSION>=:.2f}`.
```py
f"{<VARIABLE>=}"     # <VARIABLE>=<VALUE>
```

#### Date and Time Formatting
`datetime` objects accept `strftime`-style directives as their format specification.
```py
f"{<DATETIME>:%Y-%m-%d %H:%M}"
```

#### Notes
- f-strings are evaluated immediately. They cannot serve as reusable templates; use `<STRING>.format()` or `string.Template` for deferred substitution.
- f-strings are generally faster than `%` formatting and `.format()`.
- A value is formatted by calling its `__format__(<FORMAT_SPEC>)` method; custom classes may define their own specifications.
- Unlike `.format()`, f-string expressions are compiled with the surrounding code and have access to local and global scope directly.

---
## Raw Strings
A **raw string** is a string literal prefixed with `r` or `R`. Backslashes in the literal are treated as ordinary characters rather than the start of an escape sequence.
```py
RAW_STRING = r"<TEXT>"
```
- `r"\n"` is two characters: a backslash and the letter `n`. A normal `"\n"` is a single newline character.
- Raw strings are ordinary `str` objects. Only the way the literal is read by Python changes.
- Commonly used for file paths on Windows and for regular expression patterns.

#### Behaviour
- Escape sequences such as `\n`, `\t`, `\\` are not interpreted.
- A raw string **cannot end with an odd number of backslashes**. The final backslash would escape the closing quote.
- A quote can still be written inside using `\"` or `\'`, but the backslash is retained in the result.
```py
r"C:\new\table"      # 'C:\\new\\table'  (no newline, no tab)
r"\d+\.\d+"          # regex pattern, backslashes preserved
```

#### Notes
- Raw strings affect only how the **source literal** is written. A string produced at runtime (for example from `input()`) is never "raw" or "escaped".
- To end a raw string with a backslash, use concatenation or a normal string: `r"C:\folder" "\\"`.
- Use `repr()` to inspect a string and see its backslashes explicitly.

>~={purple}NOTE=~:
>Raw f-strings use `rf"..."` or `fr"..."`; backslashes in the literal text are then not treated as escapes.
---
## Unicode Strings
That means strings can represent text from many writing systems:
```
name = "प्रणीथ"
greeting = "नमस्ते"
japanese = "こんにちは"
```
Python's `str` type is designed to represent Unicode text.
This is one reason Python is convenient for internationalized applications.

# END
---
#### FOOTNOTES

