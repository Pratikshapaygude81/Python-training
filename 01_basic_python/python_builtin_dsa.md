# Python Built-in Data Structures and DSA

## 1. What is DSA?

DSA stands for **Data Structures and Algorithms**.

- **Data Structure:** A way to store and organize data.
- **Algorithm:** A step-by-step procedure to solve a problem.

Python provides built-in data structures that make storing, accessing, and processing data easier.

## 2. Python Built-in Data Structures

### 2.1 List

A list stores multiple items in an ordered, changeable collection. Duplicates are allowed.

```python
numbers = [10, 20, 30, 20]

numbers.append(40)
print(numbers)
print(numbers[0])
```

Output:

```text
[10, 20, 30, 20, 40]
10
```

Common list operations:

```python
numbers.append(50)    # Add an element
numbers.insert(0, 5)  # Insert at an index
numbers.remove(20)    # Remove the first matching value
numbers.pop()         # Remove the last element
numbers.sort()        # Sort the list
numbers.reverse()     # Reverse the list
```

### 2.2 Tuple

A tuple stores items in an ordered collection that cannot be changed after creation. Duplicates are allowed.

```python
coordinates = (10, 20, 30)

print(coordinates[0])
print(len(coordinates))
```

Output:

```text
10
3
```

Use tuples for collections of values that should remain unchanged.

### 2.3 Set

A set stores unique elements. It does not guarantee a fixed iteration order.

```python
numbers = {10, 20, 10, 30}

print(numbers)
numbers.add(40)
numbers.discard(20)
```

The set contains each value only once.

Common operations:

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)  # Union
print(a & b)  # Intersection
print(a - b)  # Difference
```

### 2.4 Dictionary

A dictionary stores data as key-value pairs. Keys must be unique.

```python
student = {
    "name": "Amit",
    "marks": 85
}

print(student["name"])
print(student.get("marks"))

student["city"] = "Pune"
```

Output:

```text
Amit
85
```

Common dictionary operations:

```python
student.keys()       # Get keys
student.values()     # Get values
student.items()      # Get key-value pairs
student.update({"marks": 90})
student.pop("city")  # Remove a key
```

## 3. Other Useful Python Types

| Type | Purpose | Example |
|---|---|---|
| `str` | Stores text | `"Python"` |
| `range` | Generates integer sequences | `range(5)` |
| `bytes` | Immutable sequence of bytes | `b"abc"` |
| `bytearray` | Mutable sequence of bytes | `bytearray(3)` |

## 4. Built-in Functions Useful in DSA

```python
numbers = [4, 2, 8, 1]

print(len(numbers))     # 4
print(sum(numbers))     # 15
print(min(numbers))     # 1
print(max(numbers))     # 8
print(sorted(numbers))  # [1, 2, 4, 8]
```

Other useful functions:

- `enumerate()` — provides an index and value while iterating.
- `zip()` — combines elements from multiple iterables.
- `any()` — returns `True` if at least one element is true.
- `all()` — returns `True` if every element is true.
- `reversed()` — provides an iterator in reverse order.

Example:

```python
names = ["Amit", "Riya", "Neha"]

for index, name in enumerate(names):
    print(index, name)
```

## 5. Useful Modules for DSA

### 5.1 `collections.deque` — Queue

A deque allows efficient insertion and removal at both ends.

```python
from collections import deque

queue = deque()

queue.append(10)
queue.append(20)

print(queue.popleft())  # 10
```

### 5.2 `collections.Counter` — Frequency Counting

```python
from collections import Counter

numbers = [1, 2, 2, 3, 3, 3]

print(Counter(numbers))
```

Output:

```text
Counter({3: 3, 2: 2, 1: 1})
```

### 5.3 `collections.defaultdict` — Default Dictionary Values

```python
from collections import defaultdict

counts = defaultdict(int)

counts["apple"] += 1
counts["apple"] += 1

print(counts["apple"])  # 2
```

### 5.4 `heapq` — Heap / Priority Queue

```python
import heapq

numbers = [5, 2, 8, 1]

heapq.heapify(numbers)

print(heapq.heappop(numbers))  # 1
```

A heap is useful when you need to retrieve the smallest element efficiently.

## 6. Common DSA Structures and Python Implementations

| DSA structure | Common Python implementation |
|---|---|
| Array / Dynamic array | `list` |
| Stack | `list` |
| Queue | `collections.deque` |
| Hash map | `dict` |
| Hash set | `set` |
| Priority queue | `heapq` |
| Linked list | Custom nodes and classes |
| Binary tree | Custom nodes and classes |
| Graph | Dictionary or adjacency lists |

## 7. Basic Time Complexity

Time complexity describes how the running time of an operation grows as the amount of data increases.

| Operation | Typical time complexity |
|---|---|
| List indexing | O(1) |
| List append | O(1) amortized |
| List search | O(n) |
| List insertion at the beginning | O(n) |
| Dictionary lookup | O(1) average |
| Set membership check | O(1) average |
| Sorting a list | O(n log n) |

These are typical complexities; actual performance can vary by operation and implementation.


## Quick Revision

- **List:** Ordered, mutable, allows duplicates.
- **Tuple:** Ordered, immutable, allows duplicates.
- **Set:** Stores unique elements.
- **Dictionary:** Stores key-value pairs with unique keys.
- **Deque:** Useful for queues and operations at both ends.
- **Counter:** Useful for frequency counting.
- **Heap:** Useful for priority queues.
- **DSA:** Helps us organize data and solve problems efficiently.
