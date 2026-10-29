# Python Dictionaries — Complete Study Notes

## 1. Introduction to Dictionaries

A dictionary is a built-in Python data type that stores information in **key-value pairs**.

Each key identifies a value, allowing us to retrieve and update information efficiently.

### Syntax

```python
dictionary_name = {
    "key1": "value1",
    "key2": "value2"
}
```

### Example

```python
student = {
    "name": "Pratiksha",
    "age": 22,
    "course": "Python"
}

print(student)
```

**Output:**

```text
{'name': 'Pratiksha', 'age': 22, 'course': 'Python'}
```

**Explanation:**
- `"name"`, `"age"`, and `"course"` are keys.
- `"Pratiksha"`, `22`, and `"Python"` are values.
- Each key is associated with a value.

## 2. Characteristics of Dictionaries

1. Dictionaries store data as key-value pairs.
2. Dictionaries are mutable, meaning their contents can be changed.
3. Keys must be unique.
4. Values can be duplicated.
5. Keys must be hashable, such as strings, integers, or suitable tuples.
6. Values can contain different data types.
7. Dictionaries preserve insertion order in modern Python.
8. Dictionaries can contain other dictionaries as values.

### Example

```python
data = {
    "name": "Amit",
    "age": 22,
    "marks": 85,
    "passed": True
}

print(data)
```

**Output:**

```text
{'name': 'Amit', 'age': 22, 'marks': 85, 'passed': True}
```

## 3. Creating Dictionaries

### Example 1: Empty dictionary

```python
student = {}

print(student)
```

**Output:**

```text
{}
```

### Example 2: Dictionary with initial values

```python
student = {
    "name": "Rahul",
    "age": 21
}

print(student)
```

**Output:**

```text
{'name': 'Rahul', 'age': 21}
```

### Example 3: Using the `dict()` function

```python
student = dict(name="Rahul", age=21)

print(student)
```

**Output:**

```text
{'name': 'Rahul', 'age': 21}
```

### Example 4: Dictionary with different data types

```python
employee = {
    "id": 101,
    "name": "Priya",
    "salary": 35000.50,
    "is_active": True,
    "skills": ["Python", "SQL"]
}

print(employee)
```

**Explanation:** Dictionary values can be integers, strings, floating-point numbers, Boolean values, lists, and other dictionaries.

## 4. Accessing Dictionary Values

### Method 1: Using square brackets

```python
student = {
    "name": "Pratiksha",
    "age": 22,
    "city": "Pune"
}

print(student["name"])
print(student["age"])
print(student["city"])
```

**Output:**

```text
Pratiksha
22
Pune
```

If the specified key does not exist, Python raises a `KeyError`.

### Method 2: Using `get()`

```python
student = {
    "name": "Pratiksha",
    "age": 22
}

print(student.get("name"))
print(student.get("marks"))
print(student.get("marks", 0))
```

**Output:**

```text
Pratiksha
None
0
```

The `get()` method returns `None` when a key is missing, unless a default value is supplied.

### Difference between `[]` and `get()`

| Square brackets | `get()` |
|---|---|
| `student["age"]` | `student.get("age")` |
| Raises `KeyError` for a missing key. | Returns `None` by default for a missing key. |
| Does not accept a separate default argument. | Can accept a default argument. |

## 5. Adding and Updating Dictionary Items

### Example 1: Adding a new item

```python
student = {
    "name": "Amit",
    "age": 21
}

student["city"] = "Pune"

print(student)
```

**Output:**

```text
{'name': 'Amit', 'age': 21, 'city': 'Pune'}
```

### Example 2: Updating an existing item

```python
student = {
    "name": "Amit",
    "age": 21
}

student["age"] = 22

print(student)
```

**Output:**

```text
{'name': 'Amit', 'age': 22}
```

### Example 3: Adding multiple items with `update()`

```python
student = {
    "name": "Amit",
    "age": 21
}

student.update({
    "age": 22,
    "city": "Pune",
    "course": "Python"
})

print(student)
```

**Output:**

```text
{'name': 'Amit', 'age': 22, 'city': 'Pune', 'course': 'Python'}
```

The `update()` method changes existing values and adds keys that are not already present.

## 6. Removing Dictionary Items

### Method 1: `pop()`

Removes a specified key and returns its value.

```python
student = {
    "name": "Amit",
    "age": 21,
    "city": "Pune"
}

removed_value = student.pop("age")

print(removed_value)
print(student)
```

**Output:**

```text
21
{'name': 'Amit', 'city': 'Pune'}
```

### Method 2: `del`

```python
student = {
    "name": "Amit",
    "age": 21
}

del student["age"]

print(student)
```

**Output:**

```text
{'name': 'Amit'}
```

### Method 3: `popitem()`

Removes and returns the last inserted key-value pair.

```python
student = {
    "name": "Amit",
    "age": 21,
    "city": "Pune"
}

print(student.popitem())
print(student)
```

**Output:**

```text
('city', 'Pune')
{'name': 'Amit', 'age': 21}
```

### Method 4: `clear()`

Removes all items without deleting the dictionary variable itself.

```python
student = {
    "name": "Amit",
    "age": 21
}

student.clear()

print(student)
```

**Output:**

```text
{}
```

## 7. Looping Through a Dictionary

A `for` loop can access dictionary keys, values, or key-value pairs.

### Example 1: Loop through keys

```python
student = {
    "name": "Amit",
    "age": 21,
    "city": "Pune"
}

for key in student:
    print(key)
```

**Output:**

```text
name
age
city
```

When we iterate directly over a dictionary, Python visits its keys.

### Example 2: Use `keys()`

```python
student = {
    "name": "Amit",
    "age": 21,
    "city": "Pune"
}

for key in student.keys():
    print(key)
```

**Output:**

```text
name
age
city
```

### Example 3: Loop through values

```python
student = {
    "name": "Amit",
    "age": 21,
    "city": "Pune"
}

for value in student.values():
    print(value)
```

**Output:**

```text
Amit
21
Pune
```

### Example 4: Loop through keys and values using `items()`

```python
student = {
    "name": "Amit",
    "age": 21,
    "city": "Pune"
}

for key, value in student.items():
    print(key, ":", value)
```

**Output:**

```text
name : Amit
age : 21
city : Pune
```

The `items()` method provides key-value pairs. Python unpacks each pair into the two loop variables.

## 8. Using `range()` with Dictionaries

We can use `range()` when we need to work with positions in a list of dictionary keys.

```python
student = {
    "name": "Amit",
    "age": 21,
    "city": "Pune"
}

keys = list(student.keys())

for i in range(len(keys)):
    print(keys[i], ":", student[keys[i]])
```

**Output:**

```text
name : Amit
age : 21
city : Pune
```

**Explanation:**
1. `student.keys()` provides the keys.
2. `list()` converts them into a list.
3. `len(keys)` returns the number of keys.
4. `range(len(keys))` generates indexes.
5. `keys[i]` retrieves a key, and `student[keys[i]]` retrieves its value.

**Note:** For ordinary dictionary iteration, `for key, value in student.items()` is generally simpler.

## 9. Checking Whether a Key or Value Exists

### Example 1: Check whether a key exists

```python
student = {
    "name": "Amit",
    "age": 21
}

if "name" in student:
    print("Name exists")

if "marks" not in student:
    print("Marks do not exist")
```

**Output:**

```text
Name exists
Marks do not exist
```

### Example 2: Check whether a value exists

```python
student = {
    "name": "Amit",
    "age": 21
}

if "Amit" in student.values():
    print("Value exists")
```

**Output:**

```text
Value exists
```

**Important:** The expression `"Amit" in student` checks dictionary keys, not values. Use `student.values()` to check values.

## 10. Nested Dictionaries

A nested dictionary is a dictionary that contains one or more dictionaries as values.

Nested dictionaries are useful for storing related information about multiple students, employees, products, or departments.

### Example 1: Basic nested dictionary

```python
students = {
    "student1": {
        "name": "Amit",
        "age": 21
    },
    "student2": {
        "name": "Priya",
        "age": 22
    }
}

print(students)
```

### Accessing values in a nested dictionary

```python
print(students["student1"]["name"])
print(students["student2"]["age"])
```

**Output:**

```text
Amit
22
```

**Explanation:**
- `students["student1"]` retrieves the inner dictionary for student 1.
- Adding `["name"]` retrieves the student's name.
- We use two sets of keys to access nested values.

### Example 2: Loop through a nested dictionary

```python
students = {
    "student1": {
        "name": "Amit",
        "marks": 85
    },
    "student2": {
        "name": "Priya",
        "marks": 92
    },
    "student3": {
        "name": "Rahul",
        "marks": 76
    }
}

for student_id, details in students.items():
    print("ID:", student_id)

    for key, value in details.items():
        print(key, ":", value)

    print()
```

**Output:**

```text
ID: student1
name : Amit
marks : 85

ID: student2
name : Priya
marks : 92

ID: student3
name : Rahul
marks : 76
```

**Explanation:**
- The outer loop visits each student.
- `details` contains the student's inner dictionary.
- The inner loop visits the fields within that dictionary.

### Example 3: Update a nested value

```python
students = {
    "student1": {
        "name": "Amit",
        "marks": 85
    }
}

students["student1"]["marks"] = 90

print(students["student1"])
```

**Output:**

```text
{'name': 'Amit', 'marks': 90}
```

### Example 4: Add a field to a nested dictionary

```python
students = {
    "student1": {
        "name": "Amit",
        "marks": 85
    }
}

students["student1"]["city"] = "Pune"

print(students["student1"])
```

**Output:**

```text
{'name': 'Amit', 'marks': 85, 'city': 'Pune'}
```

## 11. Practical Dictionary Programs

### Example 1: Store and print student marks

```python
marks = {
    "Amit": 80,
    "Priya": 90,
    "Rahul": 75
}

for name, mark in marks.items():
    print(name, "scored", mark)
```

**Output:**

```text
Amit scored 80
Priya scored 90
Rahul scored 75
```

### Example 2: Calculate total marks

```python
marks = {
    "Amit": 80,
    "Priya": 90,
    "Rahul": 75
}

total = 0

for mark in marks.values():
    total = total + mark

print("Total marks:", total)
```

**Output:**

```text
Total marks: 245
```

### Example 3: Calculate average marks

```python
marks = {
    "Amit": 80,
    "Priya": 90,
    "Rahul": 75
}

total = 0

for mark in marks.values():
    total = total + mark

average = total / len(marks)

print("Average:", average)
```

**Output:**

```text
Average: 81.66666666666667
```

### Example 4: Find the student with the highest marks

```python
marks = {
    "Amit": 80,
    "Priya": 90,
    "Rahul": 75
}

highest = None
top_student = None

for name, mark in marks.items():
    if highest is None or mark > highest:
        highest = mark
        top_student = name

print("Top student:", top_student)
print("Highest marks:", highest)
```

**Output:**

```text
Top student: Priya
Highest marks: 90
```

### Example 5: Count students who passed

Assume a student needs at least 40 marks to pass.

```python
marks = {
    "Amit": 80,
    "Priya": 90,
    "Rahul": 30,
    "Sneha": 35
}

count = 0

for mark in marks.values():
    if mark >= 40:
        count = count + 1

print("Students passed:", count)
```

**Output:**

```text
Students passed: 2
```

### Example 6: Separate passed and failed students

```python
marks = {
    "Amit": 80,
    "Priya": 30,
    "Rahul": 65,
    "Sneha": 25
}

passed = {}
failed = {}

for name, mark in marks.items():
    if mark >= 40:
        passed[name] = mark
    else:
        failed[name] = mark

print("Passed:", passed)
print("Failed:", failed)
```

**Output:**

```text
Passed: {'Amit': 80, 'Rahul': 65}
Failed: {'Priya': 30, 'Sneha': 25}
```

### Example 7: Count character frequency

```python
text = "hello"
frequency = {}

for character in text:
    if character in frequency:
        frequency[character] = frequency[character] + 1
    else:
        frequency[character] = 1

print(frequency)
```

**Output:**

```text
{'h': 1, 'e': 1, 'l': 2, 'o': 1}
```

**Explanation:**
- If the character is already present, increase its count.
- Otherwise, add the character with a count of `1`.

### Example 8: Count occurrences of numbers

```python
numbers = [1, 2, 2, 3, 1, 2, 4]
frequency = {}

for number in numbers:
    if number in frequency:
        frequency[number] = frequency[number] + 1
    else:
        frequency[number] = 1

print(frequency)
```

**Output:**

```text
{1: 2, 2: 3, 3: 1, 4: 1}
```

### Example 9: Create a dictionary from two lists

```python
names = ["Amit", "Priya", "Rahul"]
marks = [80, 90, 75]

student_marks = {}

for i in range(len(names)):
    student_marks[names[i]] = marks[i]

print(student_marks)
```

**Output:**

```text
{'Amit': 80, 'Priya': 90, 'Rahul': 75}
```

The loop uses the same index to match each name with its corresponding marks.

### Example 10: Find duplicate values

```python
numbers = [10, 20, 10, 30, 20, 40]
frequency = {}

for number in numbers:
    if number in frequency:
        frequency[number] = frequency[number] + 1
    else:
        frequency[number] = 1

for number, count in frequency.items():
    if count > 1:
        print(number, "appears", count, "times")
```

**Output:**

```text
10 appears 2 times
20 appears 2 times
```

## 12. Important Dictionary Methods

| Method | Purpose |
|---|---|
| `get(key)` | Returns a value or a default value. |
| `keys()` | Returns a view of the keys. |
| `values()` | Returns a view of the values. |
| `items()` | Returns a view of key-value pairs. |
| `update()` | Adds or updates items. |
| `pop(key)` | Removes a specified key and returns its value. |
| `popitem()` | Removes and returns the last inserted pair. |
| `clear()` | Removes all items. |
| `copy()` | Creates a shallow copy. |
| `setdefault(key, default)` | Returns the existing value or inserts the default for a missing key. |

### Example: `copy()`

```python
original = {
    "name": "Amit",
    "age": 21
}

copied = original.copy()
copied["age"] = 22

print(original)
print(copied)
```

**Output:**

```text
{'name': 'Amit', 'age': 21}
{'name': 'Amit', 'age': 22}
```

### Example: `setdefault()`

```python
student = {
    "name": "Amit"
}

student.setdefault("age", 21)
student.setdefault("name", "Rahul")

print(student)
```

**Output:**

```text
{'name': 'Amit', 'age': 21}
```

The missing `"age"` key is added, while the existing `"name"` value is not replaced.

## 13. Common Mistakes

### Mistake 1: Accessing a missing key

```python
student = {"name": "Amit"}

print(student["age"])
```

**Result:** `KeyError`, because `"age"` does not exist.

**Solution:**

```python
print(student.get("age", "Not available"))
```

### Mistake 2: Assuming duplicate keys are stored separately

```python
student = {
    "name": "Amit",
    "name": "Rahul"
}

print(student)
```

**Output:**

```text
{'name': 'Rahul'}
```

The later value replaces the earlier value for the same key.

### Mistake 3: Confusing keys and values

```python
student = {
    "name": "Amit",
    "age": 21
}

print("Amit" in student)
print("Amit" in student.values())
```

**Output:**

```text
False
True
```

### Mistake 4: Using a list as a dictionary key

Incorrect:

```python
data = {
    [1, 2]: "numbers"
}
```

This raises a `TypeError` because lists are unhashable.

Correct:

```python
data = {
    (1, 2): "numbers"
}

print(data[(1, 2)])
```

**Output:**

```text
numbers
```

A tuple can be a dictionary key when all its elements are hashable.

### Mistake 5: Dividing by zero when calculating an average

If a dictionary is empty, `len(marks)` is `0`.

Incorrect:

```python
marks = {}
average = sum(marks.values()) / len(marks)
```

This raises a `ZeroDivisionError`.

Correct:

```python
marks = {}

if len(marks) > 0:
    average = sum(marks.values()) / len(marks)
    print(average)
else:
    print("No marks available")
```

**Output:**

```text
No marks available
```

## 14. Practice Exercises

Solve the following exercises yourself.

### Part A: Dictionary Basics

1. Create a dictionary containing your name, age, city, and course.
2. Print only the keys of a dictionary.
3. Print only the values of a dictionary.
4. Add an `"email"` key to a student dictionary.
5. Update the age of a student.
6. Remove a key using `pop()`.
7. Check whether `"marks"` exists in a dictionary.
8. Access a missing key safely using `get()`.
9. Create a dictionary using the `dict()` function.
10. Copy a dictionary and update a value in the copy.

### Part B: Loops and Dictionaries

11. Print every key and value using `items()`.
12. Calculate the total of all values in a marks dictionary.
13. Calculate the average of the marks.
14. Find the student with the highest marks.
15. Count how many students passed.
16. Separate students into passed and failed dictionaries.
17. Count the frequency of each character in `"programming"`.
18. Count the frequency of numbers in `[1, 2, 2, 3, 3, 3, 4]`.
19. Create a dictionary by matching two lists.
20. Find duplicate values in a list using a dictionary.

### Part C: Nested Dictionaries

21. Create a
