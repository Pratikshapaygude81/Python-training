##  References

1. Python Official Tutorial – Modules: https://docs.python.org/3/tutorial/modules.html
2. Python Official Documentation – `__main__`: https://docs.python.org/3/library/__main__.html
3. Python Official Documentation – The Import System: https://docs.python.org/3/reference/import.html
4. Python Official Documentation – `sys.modules`: https://docs.python.org/3/library/sys.html
5. Python Packaging User Guide – Installing Packages: https://packaging.python.org/en/latest/tutorials/installing-packages/

# Python Modules

## 1. What is a Module?

A module is a Python file containing definitions and statements.

It can contain:
- Variables
- Functions
- Classes
- Executable statements

Modules help us divide a large program into smaller, manageable files. We can reuse code from one module in another program using the `import` statement.

**Example:**

Create a file named `calculator.py`:

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

This file is a module named `calculator`.

## 2. Why Do We Use Modules?

Modules are useful because they:

1. Make programs easier to organize.
2. Allow code reuse.
3. Make large programs easier to maintain.
4. Avoid writing the same code repeatedly.
5. Help divide a project into separate files.

## 3. Importing a Module

We use the `import` statement to access another module.

**Syntax:**

```python
import module_name
```

**Example:**

```python
import calculator

result = calculator.add(10, 20)

print(result)
```

**Output:**
```text
30
```

Here, `calculator` is the module name and `add()` is the function defined inside it.

We access the function using:

```python
module_name.function_name()
```

## 4. Different Ways to Import Modules

### A. Import the complete module

```python
import math

print(math.sqrt(25))
```

Output:
```text
5.0
```

### B. Import a specific function

```python
from math import sqrt

print(sqrt(25))
```

Output:
```text
5.0
```

We can use `sqrt()` directly without writing `math.sqrt()`.

### C. Import multiple functions

```python
from math import sqrt, factorial

print(sqrt(36))
print(factorial(5))
```

### D. Import using an alias

We can give a module or imported function a shorter name using `as`.

```python
import math as m

print(m.sqrt(49))
```

Output:
```text
7.0
```

We can also give an imported function an alias:

```python
from math import factorial as fact

print(fact(5))
```

Output:
```text
120
```

### E. Import all names

```python
from math import *
```

This imports names exposed by the module.

However, importing everything is generally discouraged because it can make code harder to understand and may cause naming conflicts.

## 5. Built-in and Standard Library Modules

Python provides many modules that we can use without installing additional packages.

Examples include:

| Module | Purpose |
|---|---|
| `math` | Mathematical operations |
| `random` | Generate random values |
| `datetime` | Work with dates and times |
| `os` | Interact with the operating system |
| `sys` | Access interpreter-related information |
| `statistics` | Perform statistical calculations |

**Example using the random module:**

```python
import random

number = random.randint(1, 10)

print(number)
```

This generates a random integer between 1 and 10, inclusive.

**Note:** These are commonly called standard library modules. They are provided with Python, unlike third-party packages that generally need to be installed separately.

## 6. User-Defined Modules

A user-defined module is a Python file created by the programmer to organize reusable code.

**Example:**

File 1: `greetings.py`

```python
def welcome(name):
    print("Welcome", name)
```

File 2: `main.py`

```python
import greetings

greetings.welcome("Pratiksha")
```

Output:
```text
Welcome Pratiksha
```

Both files should be in a location where Python can find the module.

## 7. The `__name__` Variable

Every Python module has a special variable called `__name__`.

Its value depends on how the module is used.

- When a module is imported, `__name__` normally contains the module's name.
- When a file is executed as the top-level program, its `__name__` is set to `"__main__"`.

**Example:**

```python
print(__name__)
```

When you execute this file directly:

```text
__main__
```

When the file is imported as a module, its `__name__` will normally be its module name.

## 8. The `if __name__ == "__main__"` Condition

This condition is used to ensure that certain code runs only when a Python file is executed directly, rather than when it is imported.

**Example:**

```python
def add(a, b):
    return a + b

if __name__ == "__main__":
    print(add(10, 20))
```

Output when executed directly:

```text
30
```

If another file imports this module, the function is available, but the `print()` statement inside the condition does not run.

**Why is it useful?**

- It separates reusable code from program execution.
- It prevents certain statements from running during import.
- It allows the same file to be used as a script and as a module.

## 9. What Happens When We Import a Module?

When Python imports a module:

1. Python searches for the requested module.
2. If it finds the module, it creates and initializes a module object.
3. The module's top-level statements are executed during its first import.
4. Python makes the module available to the importing code.

Python generally imports a module only once per interpreter session. It keeps track of imported modules in `sys.modules`.

If you modify a module while the interpreter is running, you may need to restart the interpreter or explicitly reload the module using `importlib.reload()`.

**Example:**

```python
import math
import sys

print("math" in sys.modules)
```

Output:
```text
True
```

## 10. Packages in Python

A package is a way to organize related Python modules into a hierarchical structure.

Think of it this way:

- Module = Python file
- Package = A structure that organizes modules

**Example folder structure:**

```text
mypackage/
    __init__.py
    calculator.py
    greetings.py
```

Here:
- `mypackage` is a package.
- `calculator.py` is a module.
- `greetings.py` is another module.
- `__init__.py` is commonly used to mark a regular package and can contain package initialization code.

Modern Python also supports namespace packages, which do not require an `__init__.py` file.

### Importing from a package

```python
from mypackage import calculator

print(calculator.add(10, 20))
```

## 11. Relative and Absolute Imports

Python supports two common ways to refer to modules inside packages.

**Absolute import:**

```python
from mypackage import calculator
```

This uses the full package path.

**Relative import:**

```python
from . import calculator
```

A single dot refers to the current package. Two dots can refer to the parent package.

Relative imports are useful when working with modules inside a package.

## 12. Third-Party Modules and Packages

Third-party packages are developed outside the Python standard library.

They are often installed using `pip`.

Examples:

| Package | Purpose |
|---|---|
| NumPy | Numerical computing |
| Pandas | Data analysis |
| Django | Web development |
| Flask | Web application development |
| Requests | Making HTTP requests |

**Install a package:**

```bash
pip install numpy
```

**Use the package:**

```python
import numpy

print(numpy.array([10, 20, 30]))
```

## 13. Difference Between a Module and a Package

| Module | Package |
|---|---|
| A Python module is a unit of code, commonly stored in a `.py` file. | A package organizes modules into a hierarchy. |
| Contains functions, classes and variables. | Can contain modules and subpackages. |
| Example: `calculator.py` | Example: `mypackage/` |

## 14. Important Interview Questions

**Q1. What is a module in Python?**

A module is a Python file containing functions, classes, variables and statements that can be reused in other programs.

**Q2. How do you import a module?**

Using the `import` statement.

```python
import math
```

**Q3. What is the difference between `import` and `from import`?**

`import` imports the module, while `from ... import ...` imports specific names from that module.

**Q4. What is an alias in Python?**

An alias is an alternative name given to a module or imported name using the `as` keyword.

**Q5. What is `__name__`?**

It is a special variable that identifies the module's name. When a file is executed as the top-level program, its value is `"__main__"`.

**Q6. Why do we use `if __name__ == "__main__"`?**

To execute a block of code only when the file is run directly, not when it is imported.

**Q7. What is a package?**

A package is a way to organize related modules into a hierarchical structure.

**Q8. What is pip?**

Pip is the package installer for Python. It is used to install and manage Python packages.

**Q9. What is the difference between a standard library module and a third-party package?**

Standard library modules are provided with Python. Third-party packages are developed separately and are generally installed when needed.

**Q10. What happens when a module is imported?**

Python searches for the module, initializes it, executes its top-level code on its first import, and makes it available to the importing code.

## 15. Quick Revision

| Concept | Meaning |
|---|---|
| Module | Python file containing code |
| `import` | Imports a module |
| `from ... import` | Imports specific names |
| `as` | Creates an alias |
| Standard library | Modules provided with Python |
| User-defined module | Module created by a programmer |
| Third-party package | Package developed outside the standard library |
| `__name__` | Special module variable |
| `__main__` | Name used for the top-level program |
| Package | Organizes modules |
| `pip` | Python package installer |
| `sys.modules` | Keeps track of imported modules |

