*Reference:GeeksforGeeks:https://www.geeksforgeeks.org/python/file-handling-python/*
# File Handling in Python

## 1. What is File Handling?

File handling refers to performing operations on files, such as creating, opening, reading, writing, appending, and closing them using Python.

It allows a Python program to store and retrieve data from files on a storage device.

### Need for File Handling

1. Store data permanently, even after the program ends.
2. Access external files such as `.txt`, `.csv`, and `.json`.
3. Process large files efficiently.
4. Automate tasks such as reading configuration files and saving outputs.

## 2. Opening a File

Python provides the built-in `open()` function to open a file.

### Syntax

```python
file = open("filename.txt", "mode")
```

- `filename.txt`: Name or path of the file.
- `mode`: Specifies how the file should be opened.

**Note:** If no mode is specified, Python uses read mode (`r`) by default.

### Example

```python
file = open("geek.txt", "r")
print(file)
```

**Explanation:**

- Opens `geek.txt` in read mode.
- Returns a file object if the file exists.
- Raises `FileNotFoundError` if the file does not exist.

## 3. File Modes

| Mode | Description |
|---|---|
| `r` | Opens a file for reading. File must exist. |
| `w` | Opens a file for writing. Creates it if missing; overwrites existing content. |
| `a` | Opens a file for appending. Creates it if missing. |
| `x` | Creates a new file. Raises an error if it already exists. |
| `r+` | Opens a file for both reading and writing. |
| `w+` | Opens a file for reading and writing. Overwrites existing content. |
| `a+` | Opens a file for reading and appending. |

## 4. Closing a File

The `close()` method closes an opened file and releases system resources.

### Example

```python
file = open("geek.txt", "r")

# Perform file operations

file.close()
```

**Why should we close a file?**

- Releases system resources.
- Ensures pending changes are flushed to the file.
- Prevents unnecessary resource usage.

## 5. Checking File Properties

Python provides properties to check information about an opened file.

### Example

```python
file = open("geek.txt", "r")

print("Filename:", file.name)
print("Mode:", file.mode)
print("Is Closed?", file.closed)

file.close()

print("Is Closed?", file.closed)
```

**Output:**

```text
Filename: geek.txt
Mode: r
Is Closed? False
Is Closed? True
```

### Explanation

- `file.name`: Returns the name of the file.
- `file.mode`: Returns the mode in which the file was opened.
- `file.closed`: Returns `True` if the file is closed; otherwise, `False`.

## 6. Reading a File

The `read()` method reads the contents of a file.

### Example

```python
file = open("geek.txt", "r")

content = file.read()

print(content)

file.close()
```

**Sample file content:**

```text
Hello world
GeeksforGeeks
123 456
```

**Output:**

```text
Hello world
GeeksforGeeks
123 456
```

### Other Reading Methods

| Method | Description |
|---|---|
| `read()` | Reads the entire file or a specified number of characters. |
| `readline()` | Reads one line at a time. |
| `readlines()` | Reads all lines and returns them as a list. |

### Example using readline()

```python
with open("geek.txt", "r") as file:
    print(file.readline())
```

### Example using readlines()

```python
with open("geek.txt", "r") as file:
    lines = file.readlines()
    print(lines)
```

## 7. Writing to a File

The `write()` method is used to write content into a file.

The `w` mode creates a file if it does not exist. If the file already exists, its previous content is overwritten.

### Example

```python
with open("geek.txt", "w") as file:
    file.write("Hello, Python!\n")
    file.write("File handling is easy with Python.")

print("File written successfully")
```

**Output:**

```text
File written successfully
```

**Content inside geek.txt:**

```text
Hello, Python!
File handling is easy with Python.
```

### Explanation

- `w` opens the file in write mode.
- `write()` adds content to the file.
- `\n` moves the next text to a new line.
- The previous content is overwritten when opening an existing file in `w` mode.

## 8. Appending to a File

Appending means adding new content at the end of an existing file without deleting its previous content.

We use `a` mode for appending.

### Example

```python
with open("geek.txt", "a") as file:
    file.write("\nWelcome to Python!")

print("Content appended successfully")
```

**Updated file content:**

```text
Hello, Python!
File handling is easy with Python.
Welcome to Python!
```

## 9. Using the with Statement

The `with` statement is used to open files and automatically close them after the block of code finishes.

It is generally preferred over manually calling `close()`.

### Example

```python
with open("geek.txt", "r") as file:
    content = file.read()
    print(content)
```

**Advantages:**

1. Automatically closes the file.
2. Makes code cleaner and easier to read.
3. Helps manage resources safely.
4. Closes the file even if an exception occurs inside the block.

## 10. Handling Exceptions in File Handling

Sometimes errors may occur while working with files.

Examples:
- File does not exist.
- Permission is denied.
- Invalid file operation.

We can handle these errors using `try` and `except`.

### Example

```python
try:
    with open("geek.txt", "r") as file:
        content = file.read()
        print(content)

except FileNotFoundError:
    print("Error: File not found.")

except PermissionError:
    print("Error: Permission denied.")
```

**Explanation:**

- `try`: Contains code that may generate an error.
- `except`: Handles the error.
- `FileNotFoundError`: Occurs when the requested file does not exist.
- `PermissionError`: Occurs when the program does not have the required permission.

**Note:** The `with` statement automatically closes the file, even if an exception occurs inside its block. A separate `finally` block is not required just to close a file opened using `with`.

## 11. Difference Between write() and writelines()

| `write()` | `writelines()` |
|---|---|
| Writes a string to a file. | Writes multiple strings from an iterable. |
| Usually used for one string at a time. | Useful for writing a list of strings. |
| Does not automatically add a newline. | Does not automatically add newlines either. |

### Example

```python
with open("geek.txt", "w") as file:
    file.write("Hello Python\n")

    lines = ["Welcome\n", "Learn File Handling\n"]
    file.writelines(lines)
```

## 12. Important Interview Questions

**Q1. What is file handling in Python?**

File handling is the process of creating, opening, reading, writing, and closing files using Python.

**Q2. Which function is used to open a file?**

The built-in `open()` function.

**Q3. What is the default file mode?**

The default mode is `r` (read mode).

**Q4. What is the difference between `w` and `a` mode?**

`w` overwrites existing content, whereas `a` adds new content at the end.

**Q5. Why do we use `close()`?**

To close the file and release system resources.

**Q6. What is the advantage of the `with` statement?**

It automatically closes the file after the block finishes.

**Q7. What is FileNotFoundError?**

It is an exception raised when Python cannot find the requested file.

**Q8. What is the difference between `read()` and `readline()`?**

`read()` reads the entire file or a specified number of characters, while `readline()` reads one line.

**Q9. What is the difference between `readline()` and `readlines()`?**

`readline()` returns one line, whereas `readlines()` returns all lines as a list.

**Q10. What is appending?**

Appending means adding new content at the end of an existing file without removing its previous content.

## 13. Quick Revision

| Concept | Meaning |
|---|---|
| `open()` | Opens a file |
| `close()` | Closes a file |
| `read()` | Reads file content |
| `readline()` | Reads one line |
| `readlines()` | Reads all lines into a list |
| `write()` | Writes a string |
| `writelines()` | Writes multiple strings |
| `r` | Read mode |
| `w` | Write mode |
| `a` | Append mode |
| `x` | Create a new file |
| `with` | Automatically manages file closing |
| `try-except` | Handles file-related exceptions |

## 14. References

1. Python Official Tutorial – Reading and Writing Files: https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files
2. Python Official Documentation – `open()`: https://docs.python.org/3/library/functions.html#open
3. Python Official Documentation – File Objects: https://docs.python.org/3/glossary.html#term-file-object
4. Python Official Tutorial – Errors and Exceptions: https://docs.python.org/3/tutorial/errors.html
