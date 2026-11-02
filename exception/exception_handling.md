# Exception Handling in Python

**Reference:** [W3Schools – Python Try Except](https://www.w3schools.com/python/python_try_except.asp)

## 1. What is Exception Handling?

When an error occurs while a Python program is running, Python normally stops the program and displays an error message. This error is called an **exception**.

Exception handling allows us to handle errors so that the program can respond appropriately instead of stopping unexpectedly.

Python uses these keywords for exception handling:

- `try`
- `except`
- `else`
- `finally`
- `raise`

## 2. The `try` and `except` Blocks

- The `try` block contains code that may cause an exception.
- The `except` block contains code that handles the exception.

### Example

```python
try:
    print(x)
except:
    print("An exception occurred")
```

**Output:**

```text
An exception occurred
```

**Explanation:** The variable `x` has not been defined, so `print(x)` raises a `NameError`. Python then executes the `except` block.

Without exception handling, the following code raises an error:

```python
print(x)
```

## 3. Handling Specific Exceptions

We can use different `except` blocks to handle different types of exceptions.

### Example

```python
try:
    print(x)
except NameError:
    print("Variable x is not defined")
except:
    print("Something else went wrong")
```

**Output:**

```text
Variable x is not defined
```

**Explanation:**

- `except NameError` handles an error caused by referring to an undefined variable or name.
- The general `except` block handles other exceptions not handled by the earlier specific blocks.

**Best Practice:** Catch specific exceptions whenever possible instead of using a bare `except`, because it makes errors easier to understand and debug.

## 4. The `else` Block

The `else` block runs only when no exception occurs in the `try` block.

### Example

```python
try:
    print("Hello")
except:
    print("Something went wrong")
else:
    print("Nothing went wrong")
```

**Output:**

```text
Hello
Nothing went wrong
```

**Explanation:** Since the `try` block runs without an error, the `else` block is executed.

## 5. The `finally` Block

The `finally` block runs whether an exception occurs or not.

It is commonly used for cleanup operations, such as releasing resources.

### Example

```python
try:
    print(x)
except:
    print("Something went wrong")
finally:
    print("The try-except is finished")
```

**Output:**

```text
Something went wrong
The try-except is finished
```

**Explanation:** The `try` block raises an exception because `x` is not defined. The `except` block handles it, and the `finally` block runs afterward.

## 6. Using `finally` to Close a File

A file should be closed after it has been opened so that resources are released.

### Example

```python
try:
    file = open("demofile.txt", "r")
    try:
        file.write("Lorem Ipsum")
    except:
        print("Something went wrong when writing to the file")
    finally:
        file.close()
except:
    print("Something went wrong when opening the file")
```

**Explanation:**

- The outer `try` block attempts to open the file.
- The inner `try` block attempts to write to it.
- The inner `except` block handles an error during writing.
- The inner `finally` block closes the file.
- The outer `except` block handles an error while opening the file.

**Note:** This example opens the file in read mode (`r`), so writing to it will fail. In modern Python, prefer the `with` statement for file handling because it automatically closes the file.

```python
try:
    with open("demofile.txt", "w") as file:
        file.write("Lorem Ipsum")
except OSError as error:
    print("File operation failed:", error)
```

## 7. Raising an Exception

Python allows us to raise an exception manually when a condition is not valid.

We use the `raise` keyword to raise an exception.

### Example: Raise an Exception

```python
x = -1

if x < 0:
    raise Exception("Sorry, no numbers below zero")
```

**Output:**

```text
Exception: Sorry, no numbers below zero
```

**Explanation:** Since `x` is less than zero, the condition is true and Python raises an exception with the specified message.

## 8. Raising a Specific Exception

We can raise a particular type of exception depending on the situation.

### Example: Raise a TypeError

```python
x = "hello"

if not isinstance(x, int):
    raise TypeError("Only integers are allowed")
```

**Output:**

```text
TypeError: Only integers are allowed
```

**Explanation:** The value of `x` is a string, not an integer. Therefore, the program raises a `TypeError`.

## 9. Difference Between `try`, `except`, `else`, and `finally`

| Keyword | Purpose |
|---|---|
| `try` | Contains code that may raise an exception. |
| `except` | Handles an exception raised in the `try` block. |
| `else` | Runs when no exception occurs in the `try` block. |
| `finally` | Runs whether an exception occurs or not. |
| `raise` | Manually raises an exception. |

## 10. Complete Example

```python
try:
    number = int(input("Enter a number: "))
    result = 100 / number

except ValueError:
    print("Please enter a valid integer.")

except ZeroDivisionError:
    print("You cannot divide by zero.")

else:
    print("Result:", result)

finally:
    print("Program execution completed.")
```

**Example output when the user enters `10`:**

```text
Enter a number: 10
Result: 10.0
Program execution completed.
```

**Example output when the user enters `0`:**

```text
Enter a number: 0
You cannot divide by zero.
Program execution completed.
```

## 11. Important Interview Questions

**Q1. What is exception handling in Python?**

Exception handling is a way to manage runtime errors so that a program can respond to errors instead of stopping unexpectedly.

**Q2. What is the purpose of the `try` block?**

It contains code that may raise an exception.

**Q3. What is the purpose of the `except` block?**

It handles exceptions raised inside the corresponding `try` block.

**Q4. What is the use of the `else` block?**

It executes when the `try` block completes without raising an exception.

**Q5. What is the use of the `finally` block?**

It executes whether an exception occurs or not. It is commonly used for cleanup operations.

**Q6. Can we use multiple `except` blocks?**

Yes. We can use multiple `except` blocks to handle different exception types.

**Q7. What is the `raise` keyword?**

The `raise` keyword is used to raise an exception manually.

**Q8. What is the difference between `SyntaxError` and `NameError`?**

- `SyntaxError` occurs when Python code does not follow the language syntax.
- `NameError` occurs when a name or variable is not defined.

## 12. Quick Revision

| Concept | Meaning |
|---|---|
| Exception | An error detected during program execution. |
| `try` | Tests code that may cause an exception. |
| `except` | Handles an exception. |
| `else` | Runs when no exception occurs. |
| `finally` | Runs regardless of whether an exception occurs. |
| `raise` | Manually raises an exception. |
| `NameError` | A name or variable is not defined. |
| `TypeError` | An operation is applied to an inappropriate type. |
| `ValueError` | A value has an inappropriate value for an operation. |
| `ZeroDivisionError` | Division or modulo by zero is attempted. |

## 13. References

1. [W3Schools – Python Try Except](https://www.w3schools.com/python/python_try_except.asp)
2. [Python Official Tutorial – Errors and Exceptions](https://docs.python.org/3/tutorial/errors.html)
3. [Python Official Documentation – Built-in Exceptions](https://docs.python.org/3/library/exceptions.html)