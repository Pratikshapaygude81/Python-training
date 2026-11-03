# Recursion in Python

## Reference
- [GeeksforGeeks – Recursion in Python](https://www.geeksforgeeks.org/python/recursion-in-python/)

---

## 1. Introduction to Recursion

Recursion is a programming technique in which a function calls itself either directly or indirectly to solve a problem.

It is commonly used for:

- Breaking complex problems into smaller subproblems.
- Mathematical calculations such as factorial and Fibonacci series.
- Tree and graph traversal.
- Divide-and-conquer algorithms.

## 2. Working of Recursion

A recursive function calls itself within its function body. It repeatedly solves smaller versions of the same problem until it reaches a stopping condition.

### Basic Syntax

```python
def recursive_function(parameters):
    if base_case_condition:
        return base_result
    else:
        return recursive_function(modified_parameters)
```

### Key Components of Recursion

A recursive function contains two important components:

1. **Base Case:** The condition that stops the recursive calls and prevents infinite recursion.
2. **Recursive Case:** The part of the function where it calls itself with modified parameters to solve a smaller problem.

---

## 3. Examples of Recursion

### Example 1: Factorial Using Recursion

Factorial is the product of all positive integers less than or equal to a given number.

For example:

`5! = 5 × 4 × 3 × 2 × 1 = 120`

**Program:**

```python
def factorial(n):
    if n == 0:  # Base case
        return 1
    else:       # Recursive case
        return n * factorial(n - 1)

print(factorial(5))
```

**Output:**

```text
120
```

**Explanation:**

- Base Case: When `n == 0`, the function returns `1` and stops recursion.
- Recursive Case: The function multiplies `n` by the factorial of `n - 1`.
- The function continues calling itself with smaller values until it reaches zero.

### Example 2: Fibonacci Series Using Recursion

The Fibonacci sequence is a series in which each number is the sum of the two preceding numbers, starting with `0` and `1`.

**Program:**

```python
def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)

print(fibonacci(10))
```

**Output:**

```text
55
```

**Explanation:**

- Base Cases:
  - If `n == 0`, the function returns `0`.
  - If `n == 1`, the function returns `1`.
- Recursive Case: The function calls itself twice using `fibonacci(n - 1)` and `fibonacci(n - 2)`.
- Both results are added to calculate the Fibonacci number.

---

## 4. Types of Recursion

Recursion can be broadly classified into two types based on what happens after the recursive function call.

### 4.1 Tail Recursion

Tail recursion occurs when the recursive function call is the last operation performed by the function. No additional work is required after the recursive call returns.

### 4.2 Non-Tail Recursion

Non-tail recursion occurs when the function performs additional operations after the recursive call returns.

### Example: Tail Recursion vs Non-Tail Recursion

```python
# Tail Recursion
def tail_fact(n, acc=1):
    if n == 0:
        return acc
    else:
        return tail_fact(n - 1, acc * n)


# Non-Tail Recursion
def nontail_fact(n):
    if n == 0:
        return 1
    else:
        return n * nontail_fact(n - 1)


print(tail_fact(5))
print(nontail_fact(5))
```

**Output:**

```text
120
120
```

**Explanation:**

**Tail Recursion:**

- `def tail_fact(n, acc=1)`: Defines a tail-recursive factorial function using an accumulator.
- `if n == 0: return acc`: Base case that returns the accumulated result.
- `return tail_fact(n - 1, acc * n)`: Updates the accumulator before making the recursive call.
- No additional operation is performed after the recursive call returns.

**Non-Tail Recursion:**

- `def nontail_fact(n)`: Defines a non-tail-recursive factorial function.
- `if n == 0: return 1`: Base case that returns `1`.
- `return n * nontail_fact(n - 1)`: Multiplication happens after the recursive call returns.

**Note:** Python does not perform tail call optimization. Therefore, tail recursion does not provide the same memory-saving benefits in Python that it may provide in some other programming languages.

---

## 5. When to Avoid Recursion

Recursion should be avoided in the following situations:

- When the problem can be solved easily using loops.
- When recursion depth is large and may exceed Python's recursion limit.
- When performance is critical and repeated function calls create unnecessary overhead.
- When recursion makes the program more complicated than an iterative solution.

---

## 6. Recursion vs Iteration

Recursion and iteration are two common techniques used to repeat tasks in programming.

| Feature | Recursion | Iteration |
|---|---|---|
| Method | A function calls itself repeatedly. | Uses loops such as `for` and `while`. |
| Memory Usage | Generally uses more memory because of function calls. | Generally uses less memory. |
| Performance | Usually slower due to function call overhead. | Generally faster. |
| Best Used For | Tree traversal, graph traversal and divide-and-conquer problems. | Repeating steps in a sequence. |
| Risk | May cause `RecursionError` if recursion depth is too large. | Does not have recursion-depth limitations. |

---

## 7. Key Takeaways

- Recursion is a technique in which a function calls itself.
- Every recursive function must have a base case.
- The recursive case breaks a problem into smaller subproblems.
- Tail recursion performs the recursive call as its last operation.
- Non-tail recursion performs additional operations after the recursive call.
- Python does not support tail call optimization.
- Iteration is generally more memory-efficient than recursion in Python.

---

**Reference:** [GeeksforGeeks – Recursion in Python](https://www.geeksforgeeks.org/python/recursion-in-python/)
