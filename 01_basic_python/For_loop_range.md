# Python For Loop, Range Function, Nested Loops, and Pattern Printing

## 1. Introduction to a `for` Loop

A `for` loop is a control structure used to execute a block of code repeatedly for each item in a sequence or iterable.

We use a `for` loop when we want to:
- Print numbers repeatedly.
- Access items in a list.
- Process each character in a string.
- Calculate sums and products.
- Print patterns using stars and numbers.
- Work with nested loops.

### Syntax

```python
for variable in sequence:
    statement
```

**Explanation:**
- `for` starts the loop.
- `variable` stores the current item.
- `in` connects the variable to the sequence.
- `sequence` contains the items to iterate over.
- The indented statements execute during each iteration.

### Example 1: Print numbers from a list

```python
numbers = [10, 20, 30, 40, 50]

for number in numbers:
    print(number)
```

**Output:**

```text
10
20
30
40
50
```

**Explanation:** The loop takes one number from the list at a time and prints it.

### Example 2: Iterate through a string

```python
name = "Python"

for character in name:
    print(character)
```

**Output:**

```text
P
y
t
h
o
n
```

**Explanation:** A string is a sequence of characters. The loop visits each character from left to right.

---

## 2. Understanding the `range()` Function

The `range()` function generates a sequence of integers. It is commonly used with a `for` loop when we want to repeat an operation a specific number of times.

There are three common forms of `range()`.

### A. `range(stop)`

It starts from `0` and stops before the specified number.

```python
for i in range(5):
    print(i)
```

**Output:**

```text
0
1
2
3
4
```

**Explanation:**
- The default starting value is `0`.
- The stop value is `5`.
- The number `5` is excluded.
- The loop executes five times.

### B. `range(start, stop)`

It starts from the given starting value and stops before the stop value.

```python
for i in range(1, 6):
    print(i)
```

**Output:**

```text
1
2
3
4
5
```

**Explanation:** The loop starts at `1` and stops before `6`.

### C. `range(start, stop, step)`

The `step` controls how much the number changes in each iteration.

```python
for i in range(2, 11, 2):
    print(i)
```

**Output:**

```text
2
4
6
8
10
```

The step is `2`, so each number increases by `2`.

### Example 4: Print odd numbers

```python
for i in range(1, 10, 2):
    print(i)
```

**Output:**

```text
1
3
5
7
9
```

### Example 5: Print numbers in reverse order

```python
for i in range(10, 0, -1):
    print(i)
```

**Output:**

```text
10
9
8
7
6
5
4
3
2
1
```

**Explanation:** The step is `-1`, so the value decreases by one each time.

### Important rules of `range()`

1. The stop value is excluded.
2. The default start value is `0`.
3. The default step is `1`.
4. A positive step normally moves upward.
5. A negative step moves downward.
6. The step cannot be `0`.

---

## 3. Basic Examples Using `for` and `range()`

### Example 1: Print numbers from 1 to 20

```python
for i in range(1, 21):
    print(i)
```

### Example 2: Print numbers divisible by 3

```python
for i in range(1, 31):
    if i % 3 == 0:
        print(i)
```

**Output:**

```text
3
6
9
12
15
18
21
24
27
30
```

**Explanation:** The modulo operator `%` returns the remainder. If `i % 3 == 0`, the number is divisible by `3`.

### Example 3: Print squares of numbers

```python
for i in range(1, 6):
    print(i, "square =", i * i)
```

**Output:**

```text
1 square = 1
2 square = 4
3 square = 9
4 square = 16
5 square = 25
```

### Example 4: Calculate the sum of numbers from 1 to 10

```python
total = 0

for i in range(1, 11):
    total = total + i

print("Total:", total)
```

**Output:**

```text
Total: 55
```

**Explanation:**

- Initially, `total = 0`.
- During each iteration, the current number is added to `total`.
- After the loop finishes, `total` contains the sum of all numbers from `1` to `10`.

### Example 5: Calculate the product of numbers from 1 to 5

```python
product = 1

for i in range(1, 6):
    product = product * i

print("Product:", product)
```

**Output:**

```text
Product: 120
```

This is also the factorial of `5`.

### Example 6: Print a multiplication table

```python
number = 7

for i in range(1, 11):
    print(number, "x", i, "=", number * i)
```

**Output:**

```text
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```

### Example 7: Calculate factorial

The factorial of a positive integer is the product of all positive integers up to that number.

For example:

`5! = 5 × 4 × 3 × 2 × 1 = 120`

```python
number = 5
factorial = 1

for i in range(1, number + 1):
    factorial = factorial * i

print("Factorial:", factorial)
```

**Output:**

```text
Factorial: 120
```

**Why do we initialize `factorial = 1`?**

Because factorial uses multiplication. If we initialize it to `0`, every multiplication will result in `0`.

### Example 8: Count even and odd numbers

```python
even_count = 0
odd_count = 0

for i in range(1, 11):
    if i % 2 == 0:
        even_count = even_count + 1
    else:
        odd_count = odd_count + 1

print("Even numbers:", even_count)
print("Odd numbers:", odd_count)
```

**Output:**

```text
Even numbers: 5
Odd numbers: 5
```

---

## 4. Understanding Nested `for` Loops

A **nested `for` loop** is a `for` loop written inside another `for` loop.

### Syntax

```python
for outer_variable in outer_sequence:
    for inner_variable in inner_sequence:
        statement
```

The outer loop controls the main iterations. For every iteration of the outer loop, the inner loop runs through its complete sequence.

### Example 1: Basic nested loop

```python
for i in range(1, 4):
    for j in range(1, 3):
        print(i, j)
```

**Output:**

```text
1 1
1 2
2 1
2 2
3 1
3 2
```

### Step-by-step explanation

The outer loop is:

```python
for i in range(1, 4):
```

So `i` takes the values `1`, `2`, and `3`.

The inner loop is:

```python
for j in range(1, 3):
```

So `j` takes the values `1` and `2` each time the outer loop runs.

| Outer loop `i` | Inner loop `j` values |
|---|---|
| 1 | 1, 2 |
| 2 | 1, 2 |
| 3 | 1, 2 |

The inner loop executes two times for each of the three outer-loop iterations.

Total executions of the inner loop body:

`3 × 2 = 6`

### Example 2: Print a grid of stars

```python
for i in range(3):
    for j in range(4):
        print("*", end=" ")
    print()
```

**Output:**

```text
* * * *
* * * *
* * * *
```

**Explanation:**

- The outer loop runs three times, producing three rows.
- The inner loop prints four stars in each row.
- `end=" "` keeps the stars on the same line, separated by spaces.
- The empty `print()` moves to the next line after each row is complete.

**Important:** In pattern printing, the outer loop usually controls the number of rows, and the inner loop usually controls the number of columns or symbols in each row.

---

## 5. Pattern Printing Using Nested Loops

Pattern printing is a common way to practise loops and understand how nested loops work.

Before writing a pattern program, identify:

1. How many rows are required?
2. How many symbols should appear in each row?
3. Does the number of symbols remain the same or change?
4. Should the pattern use stars, numbers, or spaces?

### Pattern 1: Square star pattern

**Pattern:**

```text
* * * *
* * * *
* * * *
* * * *
```

**Code:**

```python
for i in range(4):
    for j in range(4):
        print("*", end=" ")
    print()
```

**Explanation:**
- The outer loop runs four times.
- The inner loop prints four stars per row.
- The final `print()` moves to the next row.

Both loops use a fixed range, so every row contains the same number of stars.

### Pattern 2: Right-angled triangle

**Pattern:**

```text
*
* *
* * *
* * * *
* * * * *
```

**Code:**

```python
for i in range(1, 6):
    for j in range(i):
        print("*", end=" ")
    print()
```

**Step-by-step explanation:**

| Row `i` | Inner loop iterations | Stars printed |
|---|---:|---|
| 1 | 1 | `*` |
| 2 | 2 | `* *` |
| 3 | 3 | `* * *` |
| 4 | 4 | `* * * *` |
| 5 | 5 | `* * * * *` |

The important part is `range(i)`. The inner loop depends on the current value of the outer loop variable.

### Pattern 3: Inverted right-angled triangle

**Pattern:**

```text
* * * * *
* * * *
* * *
* *
*
```

**Code:**

```python
for i in range(5, 0, -1):
    for j in range(i):
        print("*", end=" ")
    print()
```

**Explanation:**
- The outer loop starts at `5`.
- It decreases by `1` each time.
- The inner loop prints the number of stars specified by `i`.
- Each row contains one fewer star than the previous row.

### Pattern 4: Increasing number triangle

**Pattern:**

```text
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

**Code:**

```python
for i in range(1, 6):
    for j in range(1, i + 1):
        print(j, end=" ")
    print()
```

**Explanation:**
- The outer loop determines the row.
- The inner loop prints numbers from `1` to the current row number.
- `i + 1` is used because the stop value of `range()` is excluded.

### Pattern 5: Repeated row-number triangle

**Pattern:**

```text
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```

**Code:**

```python
for i in range(1, 6):
    for j in range(i):
        print(i, end=" ")
    print()
```

**Explanation:** The inner loop prints `i`, not `j`. Therefore, each row repeats the same number.

### Pattern 6: Continuous number triangle

**Pattern:**

```text
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

**Code:**

```python
number = 1

for i in range(1, 6):
    for j in range(i):
        print(number, end=" ")
        number = number + 1
    print()
```

**Explanation:**
- `number` is initialized before both loops.
- Each time a number is printed, `number` increases by `1`.
- It is not reset at the beginning of a new row, so the counting continues.

### Pattern 7: Inverted number triangle

**Pattern:**

```text
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

**Code:**

```python
for i in range(5, 0, -1):
    for j in range(1, i + 1):
        print(j, end=" ")
    print()
```

**Explanation:** The outer loop reduces the number of columns on each row. The inner loop starts again from `1` for every row.

### Pattern 8: Pyramid pattern

**Pattern:**

```text
    *
   * *
  * * *
 * * * *
* * * * *
```

**Code:**

```python
for i in range(1, 6):
    for j in range(5 - i):
        print(" ", end="")
    for k in range(i):
        print("* ", end="")
    print()
```

**Explanation:**

This pattern uses two inner loops.

- The first inner loop prints spaces.
- The second inner loop prints stars.
- The number of spaces decreases as the row number increases.
- The number of stars increases as the row number increases.

**Important:** Spaces are what move the stars towards the centre of the output.

### Pattern 9: Inverted pyramid

**Pattern:**

```text
* * * * *
 * * * *
  * * *
   * *
    *
```

**Code:**

```python
for i in range(5, 0, -1):
    for j in range(5 - i):
        print(" ", end="")
    for k in range(i):
        print("* ", end="")
    print()
```

**Explanation:**
- The outer loop decreases the number of stars.
- The first inner loop adds more leading spaces.
- The second inner loop prints fewer stars on every new row.

### Pattern 10: Diamond pattern

**Pattern:**

```text
    *
   * *
  * * *
 * * * *
* * * * *
 * * * *
  * * *
   * *
    *
```

**Code:**

```python
# Upper half
for i in range(1, 6):
    for j in range(5 - i):
        print(" ", end="")
    for k in range(i):
        print("* ", end="")
    print()

# Lower half
for i in range(4, 0, -1):
    for j in range(5 - i):
        print(" ", end="")
    for k in range(i):
        print("* ", end="")
    print()
```

**Explanation:**
- The first outer loop creates the upper half, including the widest row.
- The second outer loop creates the lower half.
- The lower half starts at `4` so that the widest row is not printed twice.

### Pattern 11: Hollow square

**Pattern:**

```text
* * * * *
*       *
*       *
*       *
* * * * *
```

**Code:**

```python
for i in range(5):
    for j in range(5):
        if i == 0 or i == 4 or j == 0 or j == 4:
            print("*", end=" ")
        else:
            print(" ", end=" ")
    print()
```

**Explanation:**

A star is printed when the position is on:
- The first row (`i == 0`).
- The last row (`i == 4`).
- The first column (`j == 0`).
- The last column (`j == 4`).

All other positions print spaces, creating a hollow centre.

### Pattern 12: Alternating binary pattern

**Pattern:**

```text
1
0 1
1 0 1
0 1 0 1
1 0 1 0 1
```

**Code:**

```python
for i in range(1, 6):
    for j in range(i):
        print((i + j) % 2, end=" ")
    print()
```

**Explanation:**
- The outer loop determines the row.
- The inner loop determines the position in the row.
- The expression `(i + j) % 2` alternates between `0` and `1`.

---

## 6. More Examples Using Nested Loops

### Example 1: Print all pairs of numbers

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i, j)
```

**Output:**

```text
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

The outer loop runs three times and the inner loop runs three times for every outer iteration.

Total pairs: `3 × 3 = 9`.

### Example 2: Print a multiplication grid

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i * j, end="\t")
    print()
```

**Output:**

```text
1    2    3
2    4    6
3    6    9
```

**Explanation:** The outer loop selects the row number, and the inner loop selects the column number. Each cell prints the product of the two values.

### Example 3: Find common elements between two lists

```python
list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]

for i in list1:
    for j in list2:
        if i == j:
            print(i)
```

**Output:**

```text
3
4
```

**Explanation:** Each element of `list1` is compared with every element of `list2`. When two elements are equal, that value is printed.

For large lists, a set-based approach is usually more efficient, but nested loops help demonstrate the concept.

### Example 4: Print coordinates

```python
for row in range(1, 4):
    for column in range(1, 5):
        print("Row:", row, "Column:", column)
```

The outer loop produces three rows, and the inner loop produces four column positions for every row.

---

## 7. `break`, `continue`, and `pass` in a `for` Loop

### A. `break`

The `break` statement immediately terminates the nearest enclosing loop.

```python
for i in range(1, 11):
    if i == 5:
        break
    print(i)
```

**Output:**

```text
1
2
3
4
```

When `i` becomes `5`, the loop stops.

### B. `continue`

The `continue` statement skips the rest of the current iteration and moves to the next one.

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

**Output:**

```text
1
2
4
5
```

The number `3` is skipped, but the loop continues.

### C. `pass`

The `pass` statement does nothing. It can be used as a placeholder when a statement is required syntactically but the implementation is not ready.

```python
for i in range(1, 6):
    if i == 3:
        pass
    print(i)
```

**Output:**

```text
1
2
3
4
5
```

Unlike `break` and `continue`, `pass` does not stop or skip the iteration.

---

## 8. `for` Loop with Conditional Statements

A `for` loop can contain `if`, `if-else`, or `if-elif-else` statements.

### Example 1: Check whether each number is even or odd

```python
for i in range(1, 6):
    if i % 2 == 0:
        print(i, "is even")
    else:
        print(i, "is odd")
```

**Output:**

```text
1 is odd
2 is even
3 is odd
4 is even
5 is odd
```

### Example 2: Print numbers divisible by both 2 and 3

```python
for i in range(1, 31):
    if i % 2 == 0 and i % 3 == 0:
        print(i)
```

**Output:**

```text
6
12
18
24
30
```

### Example 3: Categorize marks

```python
marks = [85, 42, 29, 67, 91]

for mark in marks:
    if mark >= 75:
        print(mark, "Distinction")
    elif mark >= 40:
        print(mark, "Pass")
    else:
        print(mark, "Fail")
```

**Output:**

```text
85 Distinction
42 Pass
29 Fail
67 Pass
91 Distinction
```

---

## 9. The `else` Clause in a `for` Loop

Python allows an `else` clause after a loop. It executes when the loop finishes normally, without being terminated by `break`.

### Example

```python
for i in range(1, 4):
    print(i)
else:
    print("Loop completed")
```

**Output:**

```text
1
2
3
Loop completed
```

If the loop exits using `break`, the loop's `else` block does not execute.

```python
for i in range(1, 6):
    if i == 3:
        break
    print(i)
else:
    print("Loop completed")
```

**Output:**

```text
1
2
```

The loop ends with `break`, so `"Loop completed"` is not printed.

---

## 10. Comparing Single and Nested Loops

| Single `for` loop | Nested `for` loop |
|---|---|
| Contains one loop. | Contains a loop inside another loop. |
| Useful for processing a sequence. | Useful for grids, tables, and patterns. |
| Often processes one item per iteration. | Processes inner-loop items for each outer-loop iteration. |
| Example: printing list items. | Example: printing a star triangle. |

### Understanding execution count

```python
for i in range(4):
    print("Outer")

    for j in range(3):
        print("Inner")
```

The outer loop runs `4` times.

The inner loop runs `3` times for each outer iteration.

- Outer-loop body executions: `4`
- Inner-loop body executions: `4 × 3 = 12`

In general, when the outer loop runs `m` times and the inner loop runs `n` times for each outer iteration, the inner-loop body runs `m × n` times.

---

## 11. Common Mistakes in Loops

### Mistake 1: Forgetting that the stop value is excluded

```python
for i in range(1, 5):
    print(i)
```

Output: `1, 2, 3, 4`

To include `5`, use `range(1, 6)`.

### Mistake 2: Using a positive step for a descending range

```python
for i in range(5, 0, 1):
    print(i)
```

This produces no output because the positive step moves in the wrong direction for the specified stop value.

Correct:

```python
for i in range(5, 0, -1):
    print(i)
```

### Mistake 3: Forgetting indentation

Incorrect:

```python
for i in range(3):
print(i)
```

Correct:

```python
for i in range(3):
    print(i)
```

### Mistake 4: Forgetting the newline after a pattern row

Incorrect:

```python
for i in range(3):
    for j in range(3):
        print("*", end=" ")
```

This prints all nine stars on one line.

Correct:

```python
for i in range(3):
    for j in range(3):
        print("*", end=" ")
    print()
```

### Mistake 5: Resetting a counter inside the wrong loop

Incorrect for continuous numbering:

```python
for i in range(1, 4):
    number = 1
    for j in range(i):
        print(number, end=" ")
        number = number + 1
    print()
```

This restarts the number at `1` for each row.

Correct:

```python
number = 1

for i in range(1, 4):
    for j in range(i):
        print(number, end=" ")
        number = number + 1
    print()
```

The counter is initialized before the outer loop, so numbering continues across rows.

---

## 12. Practice Exercises

Try solving the following exercises yourself before checking other solutions.

### Part A: Basic `for` Loop and `range()`

1. Print numbers from `1` to `50`.
2. Print numbers from `50` down to `1`.
3. Print all even numbers between `1` and `100`.
4. Print all odd numbers between `1` and `50`.
5. Calculate the sum of numbers from `1` to `100`.
6. Calculate the factorial of a number entered by the user.
7. Print the multiplication table of a number entered by the user.
8. Count how many numbers between `1` and `100` are divisible by `7`.
9. Print the square and cube of each number from `1` to `10`.
10. Print all numbers between `1` and `100` that are divisible by both `3` and `5`.

### Part B: Nested Loops

11. Print a square containing four rows and four columns of stars.
12. Print all pairs `(i, j)` where `i` ranges from `1` to `3` and `j` ranges from `1` to `3`.
13. Print a multiplication grid from `1 × 1` to `5 × 5`.
14. Find common elements in two lists using nested loops.
15. Print the following pattern:

```text
*
**
***
****
*****
```

16. Print the following pattern:

```text
*****
****
***
**
*
```

17. Print the following pattern:

```text
1
12
123
1234
12345
```

18. Print the following pattern:

```text
1
22
333
4444
55555
```

19. Print a pyramid of stars.
20. Print a hollow square of stars.
21. Print a diamond of stars.
22. Print the following continuous number pattern:

```text
1
2 3
4 5 6
7 8 9 10
```

23. Print an alternating `0` and `1` triangle.
24. Create a pattern using nested loops in which the number of spaces decreases and the number of stars increases.

### Part C: Loop Control

25. Print numbers from `1` to `10`, but stop when the number reaches `6`.
26. Print numbers from `1` to `10`, skipping multiples of `3`.
27. Use a `for-else` loop to print a message when the loop completes normally.
28. Print numbers from `1` to `10`, but use `continue` to skip the number `5`.
29. Print a pattern using nested loops and an `if-else` statement.

---

## 13. Quick Revision

- A `for` loop iterates over an iterable.
- `range(stop)` starts at `0` and stops before `stop`.
- `range(start, stop)` uses a custom starting value.
- `range(start, stop, step)` controls the increment or decrement.
- Nested loops contain one loop inside another.
- The outer loop commonly controls rows in pattern printing.
- The inner loop commonly controls columns, spaces, or symbols.
- `print("*", end=" ")` prints without moving to the next line.
- An empty `print()` moves to the next line.
- `break` terminates the nearest enclosing loop.
- `continue` skips the current iteration.
- `pass` does nothing.
- A loop's `else` clause runs if the loop finishes normally without `break`.
- The inner loop executes completely for each iteration of the outer loop.

**End of Notes**
