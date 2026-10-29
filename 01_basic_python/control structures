# Control Structures in Python

## 1. Introduction

Control structures are statements that control the flow of execution of a program. They determine which statements execute, when they execute, and how many times they execute.

Python has three main types of control structures:

1. Sequential control structure
2. Selection (decision-making) control structure
3. Iteration (looping) control structure

---

## 2. Sequential Control Structure

In a sequential control structure, statements execute one after another in the order they are written.

### Example

```python
a = 10
b = 20
result = a + b

print(result)
```

### Output

```text
30
```

### Explanation

1. The variable `a` stores 10.
2. The variable `b` stores 20.
3. The addition result is stored in `result`.
4. The `print()` statement displays the result.

---

## 3. Selection Control Structure

Selection structures allow a program to make decisions based on conditions.

Python provides the following selection statements:

- `if`
- `if-else`
- `if-elif-else`
- Nested `if`

### 3.1 The if Statement

The `if` statement executes a block of code only when the given condition is true.

### Syntax

```python
if condition:
    statements
```

### Example

```python
age = 20

if age >= 18:
    print("You are eligible to vote")
```

### Output

```text
You are eligible to vote
```

### Explanation

The condition `age >= 18` is true because the age is 20. Therefore, the statement inside the `if` block executes.

### 3.2 The if-else Statement

The `if-else` statement executes one block when the condition is true and another block when it is false.

### Syntax

```python
if condition:
    statements
else:
    statements
```

### Example

```python
number = 7

if number % 2 == 0:
    print("Even number")
else:
    print("Odd number")
```

### Output

```text
Odd number
```

### Explanation

The modulus operator `%` returns the remainder after division. Since 7 divided by 2 leaves a remainder of 1, the number is odd.

### 3.3 The if-elif-else Statement

The `if-elif-else` statement checks multiple conditions in sequence.

- `if` checks the first condition.
- `elif` checks another condition if the previous condition is false.
- `else` executes if none of the preceding conditions is true.

### Example

```python
marks = 75

if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")
elif marks >= 50:
    print("Grade C")
else:
    print("Fail")
```

### Output

```text
Grade B
```

### Explanation

The first condition is false. The second condition is true, so `Grade B` is displayed and the remaining conditions are skipped.

### 3.4 Nested if Statement

A nested `if` means placing one `if` statement inside another `if` statement.

### Example

```python
age = 22
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
    else:
        print("ID required")
else:
    print("Entry not allowed")
```

### Output

```text
Entry allowed
```

### Explanation

The outer condition checks the age. The inner condition checks whether the person has identification. Both conditions are true, so entry is allowed.

---

## 4. Iteration Control Structure

Iteration means repeating a block of code multiple times.

Python provides two main loops:

1. `for` loop
2. `while` loop

### 4.1 The for Loop

A `for` loop iterates over a sequence, such as a list, string, tuple, or range of numbers.

### Syntax

```python
for variable in sequence:
    statements
```

### Example

```python
for i in range(1, 6):
    print(i)
```

### Output

```text
1
2
3
4
5
```

### Explanation

The `range(1, 6)` function generates numbers from 1 to 5. The ending value 6 is excluded.

### 4.2 The while Loop

A `while` loop repeats a block of code as long as its condition remains true.

### Syntax

```python
while condition:
    statements
```

### Example

```python
i = 1

while i <= 5:
    print(i)
    i += 1
```

### Output

```text
1
2
3
4
5
```

### Explanation

The loop starts with `i = 1`. After each iteration, `i` increases by 1. When `i` becomes 6, the condition becomes false and the loop stops.

**Important:** If the condition never becomes false, a `while` loop can run indefinitely. This is called an infinite loop.

---

## 5. Loop Control Statements

Python provides statements that change the normal execution of a loop.

### 5.1 break

The `break` statement immediately terminates the nearest enclosing loop.

```python
for i in range(1, 6):
    if i == 3:
        break
    print(i)
```

Output:

```text
1
2
```

When `i` becomes 3, the loop terminates.

### 5.2 continue

The `continue` statement skips the remaining statements in the current iteration and moves to the next iteration.

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

Output:

```text
1
2
4
5
```

The number 3 is skipped, but the loop continues.

### 5.3 pass

The `pass` statement does nothing. It is used as a placeholder when a statement is syntactically required but the implementation has not been written yet.

```python
for i in range(1, 4):
    if i == 2:
        pass
    print(i)
```

Output:

```text
1
2
3
```

Unlike `break` and `continue`, `pass` does not stop the loop or skip the current iteration.

---

## 6. Difference Between for and while Loops

| for loop | while loop |
|---|---|
| Iterates over a sequence or iterable. | Repeats while a condition is true. |
| Commonly used when iterating through items or a known range. | Commonly used when repetition depends on a condition. |
| Automatically advances to the next item. | The programmer may need to update variables manually. |
| Can also run indefinitely when used with an infinite iterator. | Can run indefinitely if the condition never becomes false. |

---

## 7. Indentation in Python

Indentation means the spaces at the beginning of a line. Python uses indentation to identify blocks of code.

### Correct Example

```python
age = 20

if age >= 18:
    print("Adult")
```

### Incorrect Example

```python
age = 20

if age >= 18:
print("Adult")
```

The incorrect example raises an `IndentationError` because the statement inside the `if` block is not indented.

Python commonly uses four spaces for each indentation level.

---

## 8. Truth Values and Conditions

Conditions evaluate to either `True` or `False`.

Comparison operators commonly used in conditions include:

| Operator | Meaning |
|---|---|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

Logical operators combine conditions:

- `and`: True when both conditions are true.
- `or`: True when at least one condition is true.
- `not`: Reverses a Boolean value.

### Example

```python
age = 22
has_id = True

if age >= 18 and has_id:
    print("Access granted")
else:
    print("Access denied")
```

Output:

```text
Access granted
```

---

## 9. Practical Examples

### Example 1: Find the Largest of Two Numbers

```python
a = 15
b = 25

if a > b:
    print("a is larger")
else:
    print("b is larger")
```

Output:

```text
b is larger
```

### Example 2: Print Even Numbers from 1 to 10

```python
for i in range(1, 11):
    if i % 2 == 0:
        print(i)
```

Output:

```text
2
4
6
8
10
```

### Example 3: Calculate the Sum of Numbers from 1 to 5

```python
total = 0

for i in range(1, 6):
    total += i

print(total)
```

Output:

```text
15
```

---

## 10. Common Errors

1. **Incorrect indentation:** Indent statements belonging to a block.
2. **Missing colon:** Add `:` after `if`, `elif`, `else`, `for`, and `while` statements.
3. **Infinite loop:** Ensure the loop condition can eventually become false when necessary.
4. **Incorrect range:** Remember that the ending value of `range()` is excluded.
5. **Using `=` instead of `==`:** Use `=` for assignment and `==` for equality comparison.

---

## 11. Interview Questions and Answers

### Q1. What are control structures?

Control structures determine the order in which statements execute in a program.

### Q2. What are the main types of control structures in Python?

Sequential, selection, and iteration.

### Q3. What is the difference between if and if-else?

`if` executes a block when a condition is true. `if-else` provides an alternative block when the condition is false.

### Q4. What is a nested if statement?

It is an `if` statement placed inside another conditional block.

### Q5. What is the difference between break and continue?

`break` terminates the loop, while `continue` skips the current iteration.

### Q6. What is the purpose of pass?

`pass` is a placeholder statement that performs no operation.

### Q7. What is an infinite loop?

An infinite loop continues running because its termination condition is never reached.

### Q8. Why is indentation important in Python?

Indentation defines code blocks and determines which statements belong to a conditional or loop.

### Q9. What does range(1, 5) return?

It generates the integers 1, 2, 3, and 4. The ending value 5 is excluded.

### Q10. Can a for loop have an else block?

Yes. A loop's `else` block executes when the loop finishes normally, but not when it terminates through `break`.

---

## 12. Practice Programs

Try solving these programs independently:

1. Check whether a number is positive, negative, or zero.
2. Check whether a number is even or odd.
3. Find the largest of three numbers.
4. Check whether a year is a leap year.
5. Print numbers from 1 to 100.
6. Print the multiplication table of a number.
7. Calculate the factorial of a number using a loop.
8. Find the sum of the digits of a number.
9. Print all even numbers between 1 and 50.
10. Print the first 10 natural numbers in reverse order.

---

## 13. Summary

- Sequential structures execute statements in order.
- Selection structures make decisions using conditions.
- Iteration structures repeat statements.
- `if`, `elif`, and `else` support decision-making.
- `for` and `while` implement loops.
- `break`, `continue`, and `pass` have different purposes.
- Indentation is essential for valid Python code.
