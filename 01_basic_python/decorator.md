## Reference

- [W3Schools – Python Decorators](https://www.w3schools.com/python/python_decorators.asp)

# Python Decorators

## 1. What is a Decorator?

A decorator is a function that takes another function as input and returns a modified or wrapped function.

Decorators allow us to add extra functionality to an existing function without changing its original source code.

## 2. Basic Decorator

A decorator is defined first and applied using `@decorator_name` above the function definition.

```python
def changecase(func):
    def myinner():
        return func().upper()
    return myinner

@changecase
def myfunction():
    return "Hello Sally"

print(myfunction())
```

**Output:**
```text
HELLO SALLY
```

**Explanation:**
- `changecase` is the decorator function.
- `myfunction` is the function being decorated.
- `func` receives the original function.
- `myinner` executes the original function and converts its return value to uppercase.
- `@changecase` applies the decorator.

## 3. Multiple Decorator Calls

The same decorator can be applied to multiple functions.

```python
def changecase(func):
    def myinner():
        return func().upper()
    return myinner

@changecase
def myfunction():
    return "Hello Sally"

@changecase
def otherfunction():
    return "I am speed!"

print(myfunction())
print(otherfunction())
```

**Output:**
```text
HELLO SALLY
I AM SPEED!
```

## 4. Arguments in Decorated Functions

If the original function accepts arguments, the wrapper function must also accept and pass those arguments.

```python
def changecase(func):
    def myinner(name):
        return func(name).upper()
    return myinner

@changecase
def myfunction(name):
    return "Hello " + name

print(myfunction("John"))
```

**Output:**
```text
HELLO JOHN
```

## 5. Using *args and **kwargs

Sometimes a decorator does not know how many arguments the original function will receive.

- `*args`: Accepts any number of positional arguments.
- `**kwargs`: Accepts any number of keyword arguments.

```python
def changecase(func):
    def myinner(*args, **kwargs):
        return func(*args, **kwargs).upper()
    return myinner

@changecase
def myfunction(name):
    return "Hello " + name

print(myfunction("John"))
```

**Output:**
```text
HELLO JOHN
```

## 6. Decorators with Arguments

A decorator can accept its own arguments by adding another outer function. This is also called a decorator factory.

```python
def changecase(n):
    def decorator(func):
        def myinner():
            if n == 1:
                result = func().lower()
            else:
                result = func().upper()
            return result
        return myinner
    return decorator

@changecase(1)
def myfunction():
    return "Hello Linus"

print(myfunction())
```

**Output:**
```text
hello linus
```

**Explanation:**
- `changecase(1)` passes the value 1 to the outer function.
- The inner decorator receives the original function.
- If `n == 1`, the result is converted to lowercase.
- Otherwise, the result is converted to uppercase.

## 7. Multiple Decorators

We can apply multiple decorators to a single function.

Decorators are applied in reverse order, starting with the decorator closest to the function.

```python
def changecase(func):
    def myinner():
        return func().upper()
    return myinner

def addgreeting(func):
    def myinner():
        return "Hello " + func() + " Have a good day!"
    return myinner

@changecase
@addgreeting
def myfunction():
    return "Tobias"

print(myfunction())
```

**Output:**
```text
HELLO TOBIAS HAVE A GOOD DAY!
```

## 8. Preserving Function Metadata

Python functions have metadata such as their name and documentation string (docstring).

The `__name__` attribute returns the function name, and `__doc__` returns its documentation string.

When a function is decorated, its original metadata may be replaced by the wrapper function's metadata.

Python provides `functools.wraps` to preserve the original function's metadata.

```python
import functools

def changecase(func):
    @functools.wraps(func)
    def myinner():
        return func().upper()
    return myinner

@changecase
def myfunction():
    "Return a greeting."
    return "Have a great day!"

print(myfunction.__name__)
print(myfunction.__doc__)
```

**Output:**
```text
myfunction
Return a greeting.
```

## 9. Key Points to Remember

1. A decorator is a function that wraps another function.
2. Decorators add extra functionality without modifying the original function's source code.
3. The `@decorator_name` syntax is used to apply a decorator.
4. The wrapper function executes the original function.
5. `*args` and `**kwargs` allow decorators to handle different types and numbers of arguments.
6. Decorators can accept their own arguments.
7. Multiple decorators are applied from bottom to top.
8. `functools.wraps` preserves the original function's metadata.

