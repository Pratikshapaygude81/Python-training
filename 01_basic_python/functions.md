# Python Functions — Lesson 1: Introduction

## 1. What is a function?

A **function** is a reusable block of code that performs a specific task. We write the code once and call the function whenever we need it.

### Without a function

```python
print("Hello, Pratiksha")
print("Welcome to Python")

print("Hello, Rahul")
print("Welcome to Python")

print("Hello, Amit")
print("Welcome to Python")
```

The same code is repeated several times.

### Using a function

```python
def greet():
    print("Hello")
    print("Welcome to Python")

greet()
greet()
greet()
```

**Output:**

```text
Hello
Welcome to Python
Hello
Welcome to Python
Hello
Welcome to Python
```

The code is written once and reused three times.

## 2. Why do we use functions?

Functions help us:

1. **Reuse code** — write once and use many times.
2. **Reduce repetition** — avoid writing the same code repeatedly.
3. **Improve readability** — make programs easier to understand.
4. **Simplify debugging** — find and fix errors more easily.
5. **Organize programs** — divide large programs into smaller tasks.

## 3. Function syntax

```python
def function_name():
    # statements
    pass

function_name()
```

| Part | Meaning |
|---|---|
| `def` | Keyword used to define a function |
| `function_name` | Name given to the function |
| `()` | Parentheses that can contain parameters |
| `:` | Marks the beginning of the function body |
| Indented statements | Code inside the function |
| `pass` | Placeholder when no code has been written yet |
| `function_name()` | Calls the function |

### Example

```python
def show_message():
    print("Learning Python")

show_message()
```

**Output:**

```text
Learning Python
```

**Important:** Defining a function does not execute its body. The body runs when the function is called.

## 4. How does a function execute?

```python
def add():
    a = 10
    b = 20
    print(a + b)

print("Start")
add()
print("End")
```

**Output:**

```text
Start
30
End
```

Execution order:

1. Python defines `add()`, but does not run its body yet.
2. `print("Start")` prints `Start`.
3. `add()` is called, so it calculates `10 + 20` and prints `30`.
4. The function finishes, and execution continues with `print("End")`.

## 5. Rules for naming functions

- Use meaningful names, such as `calculate_total()` or `display_marks()`.
- Use lowercase letters and underscores between words.
- A function name cannot start with a number.
- Do not use Python keywords such as `if`, `for`, or `return` as function names.
- Names are case-sensitive: `greet()` and `Greet()` are different names.

Examples:

```python
def calculate_salary():
    pass

def display_student_details():
    pass

def find_maximum():
    pass
```

## 6. Practical programs

### Program 1: Display details

```python
def display_details():
    print("Name: Pratiksha")
    print("Course: Computer Engineering")
    print("Goal: Python Developer")

display_details()
```

### Program 2: Print even numbers

```python
def print_even():
    for i in range(2, 11, 2):
        print(i)

print_even()
```

**Output:**

```text
2
4
6
8
10
```

### Program 3: Display a multiplication table

```python
def multiplication_table():
    for i in range(1, 11):
        print(5, "x", i, "=", 5 * i)

multiplication_table()
```

**Output:**

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

These functions perform tasks but do not accept input yet. Parameters and arguments, covered in the next lesson, allow us to pass different values to the same function.

## 7. Practice questions

Try solving these yourself:

1. Create a function that prints your name and city.
2. Create a function that prints numbers from 1 to 10.
3. Create a function that prints all odd numbers from 1 to 20.
4. Create a function that prints the squares of numbers from 1 to 5.
5. Create a function that displays the multiplication table of 7.

## 8. Quick check

What will this program print?

```python
def hello():
    print("Hello")

print("Python")
hello()
hello()
```

**Expected output:**

```text
Python
Hello
Hello
```

## Quick revision

- A function is a reusable block of code.
- Use `def` to define a function.
- Indent the statements inside the function.
- Call a function using its name followed by parentheses, such as `greet()`.
- Defining a function does not run its body; calling it does.
- Parameters and arguments let functions receive input; they will be covered next.
