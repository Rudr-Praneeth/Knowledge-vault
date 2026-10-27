# Input-Output
TAGS: #Python 
BUILT-ON: [[Python Fundamentals]]
ENABLES: - 
PREREQUSITIES: - 

---
## Input/Output
#### Interactive console I/O
`input()`, `print()`, `sys.stdin`, `sys.stdout`, `sys.stderr`
For programs that interact with a person or a terminal. 

#### File I/O
`open()`, `pathlib.Path`, text and binary files
For saving results, reading configuration, processing documents, and more.

#### Structured data I/O
`json`, `csv`, plus formats supported by other libraries
For exchanging records and structured data between systems.

#### External-system I/O
HTTP clients, sockets, database drivers, subprocesses
For communicating with APIs, databases, servers, and other programs.

----
## Interactive Console I/O
#### **PRINT FUNCTION**:
The built-in `print()` function displays information, usually in the terminal.
- `sep` controls the separator inserted between multiple arguments.
- `end` controls the last character inserted at the end of call
***Output Formatting***:
- Formatted Strings: *Learn more in [[Strings]]*
- Old-style % formatting: *Python also supports printf-style formatting* 
	- Integer: `%d`
	- Float: `%f`
	- String: `%s`
- String Format Method: *This older but still valid formatting method uses replacement fields.*
```py
"TEXT {} {}".format(VALUE_1, VALUE_2)     
"TEXT VALUE_1 VALUE_2"

"TEXT {1} {0}".format(VALUE_1, VALUE_2)           
"TEXT VALUE_2 VALUE_1"

"TEXT {NAME_1} {NAME_2}".format(NAME_1 = VALUE_1, NAME_2 = VALUE_2)
"TEXT VALUE_1 VALUE_2"
```

#### INPUT FUNCTION:
The built-in `input(USER_MESSAGE)` function reads a line of text from the user, typically through the terminal.

#### STANDARD STREAMS
A stream is a source or destination through which data flows.
Python commonly uses three standard streams for console-based programs provided through `sys` module.

~={purple}***STANDARD INPUT***=~ - `sys.stdin`
`sys.stdin` is a file-like object from which the program reads incoming text. By default, it is commonly connected to the terminal's input.
```py
import sys

INPUT = sys.stdin.read()              READS INPUT UNTILL END-OF-FILE (EOF)
INPUT = sys.stdin.readline()          READS INPUT LINE WITH \n CHARACTER
```

~={purple}***STANDARD OUTPUT***=~ - `sys.stdout` 
`sys.stdout` is the stream for normal program output.
- Unlike `print()`, `write()` does not automatically append a newline. 
- The `write()` method returns the number of characters written in text mode if the write succeeds.
```py
import sys

CHARACTER_COUNT = sys.stdout.write(STRING)
```

~={purple}***STANDARD ERROR***=~ - `sys.stderr` 
`sys.stderr` is intended for diagnostic messages, warnings, and error reporting.
Both messages might appear on the screen, but they go to different streams.
By default, `print()` writes to `sys.stdout`.
We can redirect `print()` to a file object.
```py
print("WARNING", file=sys.stderr)
```


>***NOTE***:
>Use `input()` and `print()` for ordinary beginner console programs.
>Use `sys.stdin` when reading from a stream explicitly, particularly for bulk or structured input.
>Use `sys.stdout` for controlled output without `print()`'s automatic separator and newline behavior.
>Use `sys.stderr` for diagnostic messages that should remain separate from normal results.

---
## File I/O
File inputs let's python read/load information, update information and save information for reusability. 
```py
FILE = open(PATH, MODE, ENCODING)
```
- `path` identifies the file.
- `mode` specifies how the file should be accessed.

| Mode | Purpose             | When File Exists           | When File Doesn't Exist  |
| ---- | ------------------- | -------------------------- | ------------------------ |
| "r"  | Read Text           | Reads existing content     | Raises FileNotFoundError |
| "w"  | Write Text          | Truncates existing content | Creates the file         |
| "a"  | Append Text         | Writes at the end          | Creates the file         |
| "x"  | Creates Exclusively | Raises FileNotFoundError   | Creates the file         |
| "rb" | Read Binary Data    | Reads Bytes                | Raises FileNotFoundError |
| "wb" | Write Binary Data   | Truncates existing content | Creates the file         |
| "ab" | Append Binary Data  | Appends bytes              | Creates the file         |
- `encoding` specifies how text bytes are translated into characters in text mode.

Always manage file safety using `with`
```py
with open(PATH, MODE, ENCODING) as FILE:
	## FILE OPERATIONS
```

#### File Operations
- Reading from file: `FILE.read()`
- Reading single line: `FILE.readline()`
- Collect lines into a list: `FILE.readlines()`
- Write into file: `FILE.WRITE(CONTENT)`

#### File Errors
|Error|Typical cause|
|---|---|
|`FileNotFoundError`|Reading a path that doesn't exist|
|`PermissionError`|Insufficient permission|
|`IsADirectoryError`|Trying to open a directory as a normal file|
|`UnicodeDecodeError`|Bytes cannot be decoded with the selected encoding|
#### File Paths with Pathlib
The `pathlib` module provides an object-oriented interface for file paths.
```py
from pathlib import Path

path = Path(PATH)

print(path.exists())  # CHECKS IF PATH EXISTS
print(path.name)      # RETURNS THE FILENAME COMPONENT
print(path.suffix)    # RETURNS THE FILENAME EXTENSION
```

Text I/O reads and writes strings (`str`). Python decodes incoming bytes using an encoding and encodes outgoing text. Binary I/O reads and writes bytes (`bytes`). It does not decode or encode the data as text.
The `b` prefix denotes a bytes literal.
Use text mode for ordinary text documents, source code, and text configuration. Use binary mode for images, audio, compressed files, and other data that must be preserved as bytes.

---
## Structed I/O: Json and Csv
A structured format provides rules for representing data so another program can interpret it consistently.
Two common formats are:
- JSON: represents structured values such as objects, arrays, strings, numbers, booleans, and null.
- CSV: represents tabular data as rows and fields.

#### JSON - JavaScript Object Notation
JSON is a text format used for configuration files, API responses, and exchanging structured information between programs.
The JSON format supports a limited set of data types. Python values are mapped to those JSON types during serialization.

| Python Value/Type | JSON Representation |
| ----------------- | ------------------- |
| `dict`            | Object              |
| `list`            | Array               |
| `str`             | String              |
| `int`             | Number              |
| `float`           | Number              |
| `True`/`False`    | true/false          |
| `None`            | null                |
A Python tuple is normally serialized as a JSON array. JSON does not preserve the distinction between a Python list and a tuple.
Similarly, sets and arbitrary custom Python objects do not automatically have a standard JSON representation.

~={purple}***JSON Operations***=~:
1. Writing Json into Files: Using `dump` method which serialises the python dictionary object. Serialization is converting a data structure into a representation suitable for storage or transmission.
   ```py
   import json
   
   with open(PATH, "w" (MODE), encoding="utf-8") as FILE:
	   json.dump(PYTHON_DICTIONARY, FILE, INDENT=n)
   ```
2. Reading Json from Files: Using `load` method which deserializes the Json data. Deserialization means reconstructing a value from a serialized representation.
   ```py
   import json
   
   with open(PATH, "r" (MODE), encoding="utf-8") as FILE:
	   PYTHON_DICTIONARY = json.load(FILE)
   ```

|Function|Input|Result or destination|
|---|---|---|
|`json.dump(obj, file)`|Python object|Writes JSON to a file|
|`json.dumps(obj)`|Python object|Returns JSON text as a string|
|`json.load(file)`|File containing JSON|Returns a Python value|
|`json.loads(text)`|JSON string|Returns a Python value|

#### Comma Separated Values - CSV
CSV is commonly used for tabular data, spreadsheets, and data exchange.
Unlike JSON, CSV does not have a rich built-in type system. Fields are fundamentally text values, and your program must decide how to interpret them.
CSV is useful for exporting reports, importing spreadsheet data, and exchanging rows between systems. 
~={purple}***CSV Operations***=~:
- CSV Writing and Reading
```py
import csv

DATA = [
	["COLUMN_1", "COLUMN_2", ...],
	["VALUE_01", "VALUE_02", ...],
	["VALUE_11", "VALUE_12", ...],
]

with open(PATH, MODE, ENCODING) as FILE:
	WRITER = csv.writer(FILE) #Creates a writer associated with the file.
	WRITER.writerows(DATA)
	
	READER = csv.reader(FILE)
	
	HEADER_ROW = next(READER) 
	# Retrieves the next row from the reader.
	# Here, it retrieves the header
    for row in READER:
        print(row)
        
    DICT_READER = csv.DictReader(FILE) 
    # Each row is provided as dictionary keyed by column name.
    for row in DICT_READER:
	    print(row["COLUMN_1"])
	
	DICT_WRITER = csv.DICT_WRITER(FILE, feildnames=HEADER_ROW)
	# Feildnames define column names (*in order)
	DICT_WRITER.writeheader()
	DICT_WRITER.writerows(DATA)
    
```

