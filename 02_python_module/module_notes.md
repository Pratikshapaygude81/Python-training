
# Python Modules – Complete Notes

## 1. What is a Module?

A module in Python is a file containing Python code such as variables, functions, and classes that can be reused in other Python programs.

Modules help us:
- Organize code into separate files.
- Reuse code instead of writing it again.
- Make programs easier to maintain.
- Keep large projects organized.

**Example:**

Suppose we have two Python files:

```text
project/
    calculator.py
    main.py
```

`calculator.py` contains reusable functions, and `main.py` imports and uses them.

---

## 2. Types of Python Modules

Python modules are mainly classified into three types:

### A. Built-in Modules

These modules are already provided by Python. We can directly import and use them.

Examples:

| Module | Purpose |
|---|---|
| math | Mathematical operations |
| random | Generate random values |
| os | Interact with the operating system |
| datetime | Work with dates and times |
| sys | Access Python interpreter information |
| json | Work with JSON data |
| statistics | Perform statistical calculations |

**Example using math module:**

```python
import math

print(math.sqrt(25))
print(math.factorial(5))
print(math.pi)
```

Output:

```text
5.0
120
3.141592653589793
```

### B. User-Defined Modules

A user-defined module is a Python file created by a programmer to store reusable code.

**Example:**

File 1: `calculator.py`

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

File 2: `main.py`

```python
import calculator

print(calculator.add(10, 5))
print(calculator.subtract(10, 5))
```

Output:

```text
15
5
```

Here, `calculator.py` is a user-defined module.

### C. Third-Party Modules

These modules are developed by external developers or organizations. They are not included in the standard Python installation and may need to be installed separately.

Examples:

| Module | Purpose |
|---|---|
| numpy | Numerical calculations |
| pandas | Data manipulation and analysis |
| requests | Making HTTP requests |
| matplotlib | Data visualization |
| flask | Web application development |
| django | Web application development |

**Installation example:**

```bash
pip install pandas
```

**Usage:**

```python
import pandas as pd

data = [10, 20, 30]

series = pd.Series(data)

print(series)
```

---

## 3. Different Ways to Import Modules

### A. Import the Complete Module

Syntax:

```python
import module_name
```

Example:

```python
import math

print(math.sqrt(36))
```

Output:

```text
6.0
```

We use the module name followed by a dot to access its functions.

### B. Import a Specific Function

Syntax:

```python
from module_name import function_name
```

Example:

```python
from math import sqrt

print(sqrt(49))
```

Output:

```text
7.0
```

We can directly use `sqrt()` without writing `math.sqrt()`.

### C. Import Multiple Functions

```python
from math import sqrt, factorial

print(sqrt(64))
print(factorial(5))
```

### D. Import Using an Alias

An alias is an alternative name given to a module or function.

Syntax:

```python
import module_name as alias
```

Example:

```python
import math as m

print(m.sqrt(81))
```

Output:

```text
9.0
```

Another example:

```python
import pandas as pd
```

Here, `pd` is the commonly used alias for pandas.

### E. Import All Functions

```python
from math import *

print(sqrt(25))
print(factorial(5))
```

This imports all public names from the module.

**Note:** Using `from module import *` is generally discouraged because it can create naming conflicts and make code difficult to understand.

---

## 4. The dir() Function

The `dir()` function displays the names available in a module or object.

Example:

```python
import math

print(dir(math))
```

It displays the available functions, constants, and other attributes of the math module.

---

## 5. The help() Function

The `help()` function provides documentation about a module, function, or object.

Example:

```python
import math

help(math)
```

For a specific function:

```python
help(math.sqrt)
```

---

## 6. The __name__ Variable

Every Python module has a special variable called `__name__`.

When a Python file is executed directly, its `__name__` value is:

```python
"__main__"
```

When the file is imported into another module, its `__name__` is usually its module name.

**Example:**

File: `calculator.py`

```python
def add(a, b):
    return a + b

print(__name__)

if __name__ == "__main__":
    print(add(10, 20))
```

If we run `calculator.py` directly, output:

```text
__main__
30
```

If another file imports it:

```python
import calculator
```

The module's `__name__` is `calculator`, so the code inside the `if` block does not execute.

**Why do we use it?**

- To prevent certain code from running when a module is imported.
- To separate reusable code from testing or execution code.
- To control the starting point of a Python program.

---

## 7. Difference Between Module, Package and Library

| Term | Meaning | Example |
|---|---|---|
| Module | A Python file containing reusable code | math.py |
| Package | A collection of related Python modules | A package containing several modules |
| Library | A collection of reusable code and packages | NumPy, Pandas |

### Module example

```text
calculator.py
```

### Package example

```text
mypackage/
    __init__.py
    addition.py
    subtraction.py
```

A package helps organize related modules.

---

## 8. What is pip?

Pip is Python's package installer. It is used to install and manage third-party packages.

### Check pip version

```bash
pip --version
```

### Install a package

```bash
pip install requests
```

### Install a specific version

```bash
pip install requests==2.32.3
```

### Upgrade a package

```bash
pip install --upgrade requests
```

### Uninstall a package

```bash
pip uninstall requests
```

### List installed packages

```bash
pip list
```

### Display package details

```bash
pip show requests
```

---

## 9. What is __pycache__?

When Python imports a module, it may generate compiled bytecode files to help Python load the module more efficiently.

These files are commonly stored in a folder named:

```text
__pycache__/
```

Example:

```text
project/
    calculator.py
    __pycache__/
        calculator.cpython-312.pyc
```

The `.pyc` file contains compiled Python bytecode.

We generally do not need to create or manage this folder manually.

---

## 10. Advantages of Modules

1. Code reusability – Write code once and use it in multiple files.
2. Better organization – Divide a large program into smaller files.
3. Easy maintenance – Changes can be made in individual modules.
4. Readability – Makes code easier to understand.
5. Less duplication – Avoid writing the same code repeatedly.
6. Collaboration – Different developers can work on different modules.

---

## 11. Important Interview Questions

### Q1. What is a module in Python?

A module is a Python file containing reusable code such as functions, variables, and classes.

### Q2. What are the types of Python modules?

There are three main types:
- Built-in modules
- User-defined modules
- Third-party modules

### Q3. What is the difference between import and from import?

`import math` imports the complete module, and we access functions using `math.sqrt()`.

`from math import sqrt` imports only the specified function, and we can directly use `sqrt()`.

### Q4. What is an alias in Python?

An alias is an alternative name given to a module or function using the `as` keyword.

Example:

```python
import numpy as np
```

### Q5. What is pip?

Pip is Python's package installer used to install, upgrade, and uninstall third-party packages.

### Q6. What is the difference between a module and a package?

A module is a single Python file, whereas a package organizes multiple related modules.

### Q7. What is the purpose of __name__ == "__main__"?

It checks whether a Python file is being executed directly. It helps prevent certain code from running when the file is imported.

### Q8. What is the purpose of dir()?

It displays the available names and attributes of a module or object.

### Q9. What is the purpose of help()?

It displays documentation and information about modules, functions, and objects.

### Q10. Can we create our own modules?

Yes. We can create a Python file containing functions, variables, or classes and import it into another Python file.

---

## 12. Practical Programs

### Program 1: Calculate Square Root Using math

```python
import math

number = 144

print("Square root:", math.sqrt(number))
```

### Program 2: Generate Random Numbers

```python
import random

number = random.randint(1, 100)

print("Random number:", number)
```

### Program 3: Display Current Date and Time

```python
import datetime

current_date = datetime.datetime.now()

print(current_date)
```

### Program 4: Create a User-Defined Module

File: `greeting.py`

```python
def greet(name):
    print("Hello", name)
```

File: `main.py`

```python
import greeting

greeting.greet("Pratiksha")
```

Output:

```text
Hello Pratiksha
```

---

## 13. Quick Revision

| Concept | Meaning |
|---|---|
| Module | Python file containing reusable code |
| Built-in module | Module provided by Python |
| User-defined module | Module created by the programmer |
| Third-party module | Module developed externally |
| import | Imports a module |
| from...import | Imports selected names |
| as | Creates an alias |
| dir() | Displays available names |
| help() | Displays documentation |
| pip | Python package installer |
| __name__ | Special variable containing module name |
| __pycache__ | Folder containing cached bytecode files |

