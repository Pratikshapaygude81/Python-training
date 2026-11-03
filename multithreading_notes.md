*Reference:Geeksforgeeks https://www.geeksforgeeks.org/python/multithreading-python-set-1/*
## Multithreading in Python
Multithreading in Python allows multiple threads (smaller units of a process) to run concurrently, enabling efficient multitasking. 
It is especially useful for I/O-bound tasks like file handling, network requests, or user interactions.

What is a Process?
A process is an executing program with:

Program code (instructions to run)
Data (variables, buffers, workspace)
Execution context (state of the process)
What is a Thread?
A thread is the smallest unit of execution inside a process.

A process can have multiple threads.
Threads share the same code and global data but have their own registers and local variables (stack).
Think of a thread as a lightweight subprocess.
Consider the diagram below to understand the relationship between the process and its thread:

multithreading-python-11
Relationship between a Process and its Thread
In the diagram:

A process is managed by a PCB.
Each thread is managed by a TCB and linked to its process.
Threads share the process’s code and data but have their own stacks.
How Multithreading Works
On single-core CPUs, Python achieves concurrency using context switching (frequent switching between threads).
This makes threads appear to run in parallel (multitasking).
Multiple threads help in performing background tasks without blocking the main program.
Consider the diagram below to understand how multiple threads exist in memory:

multithreading-python-21
Singke-threaded vs. multithreaded
A single-threaded process executes only one task at a time.
A multithreaded process can run multiple tasks in parallel by having separate stacks/registers for each thread, but sharing the same code and data.
Threading in Python
Python provides the threading module to work with threads.

Steps to Create and Run Threads
1: Import the module

import threading

2: Create threads

t1 = threading.Thread(target=func1, args=(...,))
t2 = threading.Thread(target=func2, args=(...,))

3: Start threads

t1.start()
t2.start()

4: Wait for completion

t1.join()
t2.join()

Example:





import threading
import time
​
def square(num):
    print(f"Square: {num*num}")
    time.sleep(1)
​
def cube(num):
    print(f"Cube: {num*num*num}")
    time.sleep(1)
​
t1 = threading.Thread(target=square, args=(4,))
t2 = threading.Thread(target=cube, args=(4,))
​
t1.start()
t2.start()
t1.join()
t2.join()
​
print("Done!")
Since both threads (t1 and t2) run concurrently, the order of execution is not fixed. The output may look like either of these:

Square: 16
Cube: 64
Done!

ThreadPoolExecutor (Simpler Thread Management)
The concurrent.futures.ThreadPoolExecutor makes it easier to manage multiple threads without manually creating them.

Example:





from concurrent.futures import ThreadPoolExecutor
​
def worker(task):
    print(f"Task {task} running")
​
# Create a thread pool with 2 workers
with ThreadPoolExecutor(max_workers=2) as executor:
    # Submit two tasks to run in parallel
    executor.submit(worker, 1)
    executor.submit(worker, 2)
Explanation:

Creates a thread pool with 2 worker threads.
Submits two tasks to run in parallel.
Each task prints a message (Task 1 running, Task 2 running).
The thread pool manages execution and shuts down automatically.
