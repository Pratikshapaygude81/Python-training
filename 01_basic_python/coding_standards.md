
# Python Coding Standards and Best Practices

## 1. What are Coding Standards?

Coding standards are a set of rules and guidelines that developers follow while writing code.

They help developers write code that is:
- Readable
- Understandable
- Consistent
- Reusable
- Easy to maintain
- Less error-prone

**Example:**

Without proper naming:
```python
x = 10
y = 20
z = x + y
print(z)
```

With proper naming:
```python
first_number = 10
second_number = 20
total = first_number + second_number

print(total)
```

The second example is easier to understand.

---

## 2. PEP 8 – Python Style Guide

PEP 8 stands for Python Enhancement Proposal 8.

It is the official Python style guide that provides recommendations for writing clean and readable Python code.

It covers:
- Naming conventions
- Indentation
- Line length
- Spacing
- Imports
- Comments
- Code organization

---

## 3. Indentation

Indentation means adding spaces at the beginning of a line.

Python uses indentation to define blocks of code.

**Standard:** Use 4 spaces for each indentation level.

Correct:
```python
if age >= 18:
    print("Eligible to vote")
```

Incorrect:
```python
if age >= 18:
print("Eligible to vote")
```

Incorrect indentation can cause an IndentationError.

---

## 4. Naming Conventions

Naming conventions are rules used to name variables, functions, classes, and constants.

### A. Variable Names

Use lowercase letters and underscores.

This style is called snake_case.

Correct:
```python
student_name = "Pratiksha"
student_age = 22
total_marks = 450
```

Avoid:
```python
StudentName = "Pratiksha"
studentAge = 22
```

### B. Function Names

Function names should also use snake_case.

Correct:
```python
def calculate_total():
    pass

def display_student_details():
    pass
```

### C. Class Names

Class names should use PascalCase.

Correct:
```python
class StudentDetails:
    pass

class EmployeeManagement:
    pass
```

### D. Constants

Constants are generally written using uppercase letters with underscores.

Correct:
```python
PI = 3.14159
MAX_USERS = 100
DATABASE_NAME = "student_db"
```

### Naming Convention Summary

| Element | Convention | Example |
|---|---|---|
| Variable | snake_case | student_name |
| Function | snake_case | calculate_total() |
| Class | PascalCase | StudentDetails |
| Constant | UPPER_CASE | MAX_SIZE |
| Module | lowercase | calculator.py |
| Package | lowercase | student_management |

---

## 5. Comments

Comments explain the purpose or logic of code.

Python ignores comments during execution.

### Single-line Comments

Use the # symbol.

```python
# Calculate the total of two numbers
first_number = 10
second_number = 20

total = first_number + second_number
```

### Multi-line Comments

Multiple single-line comments can be used.

```python
# This program calculates the
# total of two numbers and
# displays the result.
```

---

## 6. Docstrings

A docstring is a string used to describe a module, class, or function.

Docstrings are written using triple quotation marks.

Example:
```python
def calculate_sum(a, b):
    """
    Calculate the sum of two numbers.

    Args:
        a: First number.
        b: Second number.

    Returns:
        Sum of the two numbers.
    """
    return a + b
```

Difference:

- Comments explain code to developers.
- Docstrings document modules, classes, and functions and can be accessed through documentation tools.

---

## 7. Line Length

PEP 8 recommends limiting most lines to 79 characters.

For longer statements, use parentheses to split the expression.

Example:

```python
total_amount = (
    product_price
    + delivery_charge
    + tax_amount
)
```

This makes long statements easier to read.

---

## 8. Blank Lines and Spacing

Use blank lines to separate logical sections of code.

PEP 8 recommends:
- Two blank lines between top-level function and class definitions.
- One blank line between methods inside a class.

### Correct spacing

```python
first_number = 10
second_number = 20

total = first_number + second_number
print(total)
```

### Spaces around operators

Correct:
```python
total = 10 + 20
```

Avoid:
```python
total=10+20
```

---

## 9. Import Statements

Imports should generally be placed at the top of the Python file.

Organize imports in this order:

1. Standard library imports.
2. Third-party imports.
3. Local application imports.

Example:

```python
# Standard library imports
import os
import math

# Third-party imports
import pandas as pd

# Local application imports
from calculator import add
```

Avoid unnecessary or unused imports.

---

## 10. Avoid Hardcoding Values

Hardcoding means directly writing fixed values throughout the program.

Instead, use variables and constants.

Avoid:
```python
area = 3.14 * 5 * 5
```

Better:
```python
PI = 3.14
radius = 5

area = PI * radius * radius
```

Benefits:
- Easier to update values.
- Improves readability.
- Reduces repeated values.

---

## 11. Write Reusable Functions

Avoid repeating the same code multiple times.

Create functions for reusable logic.

Without a function:
```python
a = 10
b = 20
print(a + b)

x = 30
y = 40
print(x + y)
```

With a function:
```python
def add_numbers(a, b):
    return a + b

print(add_numbers(10, 20))
print(add_numbers(30, 40))
```

Benefits:
- Code reusability.
- Less duplication.
- Easier testing.
- Better maintenance.

---

## 12. Exception Handling

Use exception handling to manage runtime errors without abruptly stopping the program.

Python provides:
- try
- except
- else
- finally

Example:

```python
try:
    number = int(input("Enter a number: "))
    result = 100 / number

except ValueError:
    print("Please enter a valid number.")

except ZeroDivisionError:
    print("Cannot divide by zero.")

else:
    print("Result:", result)

finally:
    print("Program completed.")
```

Best practices:
- Catch specific exceptions.
- Avoid unnecessary exception handling.
- Do not silently ignore errors.
- Provide meaningful error messages.

---

## 13. Avoid Unnecessary Code

Write simple and clear code.

Avoid unnecessary variables, repeated statements, and complicated expressions.

Example:

Unnecessary:
```python
first_number = 10
second_number = 20
result = first_number + second_number
print(result)
```

For a simple calculation, this is also valid:

```python
print(10 + 20)
```

Choose the approach that makes the program easiest to understand and maintain.

---

## 14. Use Meaningful Function and Variable Names

Names should clearly describe their purpose.

Avoid:
```python
def f(x, y):
    return x * y
```

Better:
```python
def calculate_area(length, width):
    return length * width
```

Meaningful names make code easier to understand.

---

## 15. Code Organization

Organize code into separate files and folders based on functionality.

Example:

```text
student_management/
    main.py
    student.py
    database.py
    utilities.py
    README.md
```

Benefits:
- Easy navigation.
- Better code maintenance.
- Easier collaboration.
- Clear separation of responsibilities.

---

## 16. Use Virtual Environments

A virtual environment creates an isolated Python environment for a project.

It helps manage project-specific dependencies.

Create a virtual environment:

```bash
python -m venv venv
```

Activate in Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

Activate in Windows CMD:

```cmd
venv\Scripts\activate
```

Install a package:

```bash
pip install requests
```

Deactivate:

```bash
deactivate
```

---

## 17. Testing Your Code

Testing checks whether code works as expected.

Python provides a built-in testing framework called unittest.

Example:

```python
import unittest

def add_numbers(a, b):
    return a + b

class TestAddition(unittest.TestCase):

    def test_addition(self):
        self.assertEqual(add_numbers(10, 20), 30)

if __name__ == "__main__":
    unittest.main()
```

Testing helps:
- Find bugs.
- Verify expected results.
- Prevent future errors.
- Improve code reliability.

---

## 18. Code Formatting and Linting Tools

Tools help developers maintain consistent coding styles.

### A. Black

Black is an automatic Python code formatter.

Installation:
```bash
pip install black
```

Format a file:
```bash
black filename.py
```

### B. Flake8

Flake8 checks code style and identifies common programming issues.

Installation:
```bash
pip install flake8
```

Check a file:
```bash
flake8 filename.py
```

### C. Pylint

Pylint analyzes Python code and reports potential errors and style problems.

Installation:
```bash
pip install pylint
```

Check a file:
```bash
pylint filename.py
```

---

## 19. Advantages of Following Coding Standards

1. Improves code readability.
2. Makes maintenance easier.
3. Reduces code duplication.
4. Helps developers collaborate.
5. Makes debugging easier.
6. Improves code quality.
7. Makes projects more professional.

---

## 20. Important Interview Questions

### Q1. What are coding standards?

Coding standards are guidelines that help developers write readable, consistent, and maintainable code.

### Q2. What is PEP 8?

PEP 8 is the Python style guide that provides recommendations for writing clean and readable Python code.

### Q3. What is indentation in Python?

Indentation means spaces at the beginning of a line. Python uses indentation to define code blocks.

### Q4. What is the standard indentation in Python?

Four spaces per indentation level.

### Q5. What is snake_case?

A naming convention in which words are written in lowercase and separated by underscores.

Example: student_name.

### Q6. What is PascalCase?

A naming convention in which each word starts with a capital letter.

Example: StudentDetails.

### Q7. What is a docstring?

A docstring is documentation written inside a module, class, or function using string literals, commonly triple quotation marks.

### Q8. What is the difference between comments and docstrings?

Comments explain code, while docstrings document modules, classes, and functions.

### Q9. Why should we avoid hardcoding?

Avoiding hardcoding makes programs easier to update, reuse, and maintain.

### Q10. What is Black?

Black is an automatic Python code formatting tool.

### Q11. What is Flake8?

Flake8 is a tool that checks Python code for style violations and common issues.

### Q12. What is a virtual environment?

A virtual environment is an isolated Python environment used to manage dependencies for a particular project.

### Q13. Why should we use meaningful variable names?

Meaningful names make code easier to understand, debug, and maintain.

### Q14. Why is exception handling important?

It helps manage runtime errors and allows programs to handle unexpected situations gracefully.

---

## 21. Quick Revision Table

| Concept | Meaning |
|---|---|
| Coding Standards | Guidelines for writing clean code |
| PEP 8 | Python style guide |
| Indentation | Spaces used to define code blocks |
| snake_case | Variable and function naming style |
| PascalCase | Class naming style |
| UPPER_CASE | Constant naming style |
| Comments | Explanations inside code |
| Docstrings | Documentation for modules, classes, and functions |
| Black | Code formatter |
| Flake8 | Code style checker |
| Pylint | Python code analyzer |
| unittest | Python testing framework |
| Virtual Environment | Isolated project environment |

---

## 22. Practice Checklist

- [ ] Understand coding standards.
- [ ] Learn PEP 8 guidelines.
- [ ] Practise proper indentation.
- [ ] Follow naming conventions.
- [ ] Write comments and docstrings.
- [ ] Practise proper spacing and line length.
- [ ] Organize import statements.
- [ ] Write reusable functions.
- [ ] Practise exception handling.
- [ ] Learn virtual environments.
- [ ] Understand testing.
- [ ] Explore Black, Flake8, and Pylint.
- [ ] Prepare interview questions.
