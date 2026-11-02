Context Manager in Python

In any programming language, usage of resources like file operations or database connections is very common, but limited. Therefore, main problem lies in making sure to release these resources after usage. If they are not released then it will lead to resource leakage and may cause system to either slow down or crash.
Python’s context managers provide a neat way to automatically set up and clean up resources, ensuring they’re properly managed even if errors occur.

Why Do We Need Context Managers?
Automatic cleanup: Frees resources like files or connections without manual effort.
Avoid resource leaks: Ensures proper release, even if errors occur.
Cleaner code: Replaces verbose try-finally blocks with with.
Exception-safe: Always performs cleanup, even on exceptions.
Custom control: Lets you manage any resource using __enter__ and __exit__.
Risks of Not Closing Resources
Failing to close resources like files can lead to serious issues, such as exhausting available system file descriptors. This can cause your program or even the entire system to slow down or crash.

Example: This code repeatedly opens a file without closing it, leading to resource exhaustion and a potential system error.


file_descriptors = []
for x in range(100000):
    file_descriptors.append(open('test.txt', 'w'))
This will raise:

Traceback (most recent call last):
  File "context.py", line 3, in 
OSError: [Errno 24] Too many open files: 'test.txt'

This happens because too many files are left open without being closed, something context managers help avoid.

Built-in Context Manager for File Handling
File operations are a common case in Python where proper resource management is crucial. The with statement provides a built-in context manager that ensures file is automatically closed once you're done with it, even if an error occurs.

Example: In this Example, we open a file using a context manager with statement and reads its content safely.


with open("test.txt") as f:
    data = f.read()
This eliminates need to explicitly call close() and protects against resource leakage in case of unexpected failures.

Creating Custom Context Manager Class
A class-based context manager needs two methods:

__enter__(): sets up the resource and returns it.
__exit__(): cleans up the resource (e.g., closes a file).
Example:

The below example, shows how Python initializes the object, enters the context, runs the block and then exits while cleaning up.


class ContextManager:
    def __init__(self):
        print('init method called')
        
    def __enter__(self):
        print('enter method called')
        return self
    
    def __exit__(self, exc_type, exc_value, exc_traceback):
        print('exit method called')

with ContextManager() as manager:
    print('with statement block')
Output:

init method called
enter method called
with statement block
exit method called

Explanation:

__init__() initializes the object.
__enter__() runs at the start of the with block and returns the object.
The block executes (print statement).
__exit__() is called after the block ends to handle cleanup.
File Management Using Context Manager
Applying the concept of custom context managers, this example defines a FileManager class to handle opening, reading/writing and automatically closing a file.

Example:


class FileManager:
    def __init__(self, filename, mode):
        self.filename = filename
        self.mode = mode
        self.file = None
        
    def __enter__(self):
        self.file = open(self.filename, self.mode)
        return self.file
    
    def __exit__(self, exc_type, exc_value, exc_traceback):
        self.file.close()

with FileManager('test.txt', 'w') as f:
    f.write('Test')
print(f.closed)
Output:

True 

Explanation:

__enter__() opens the file and returns it.
Inside the with block, you can use the file object.
__exit__() ensures the file is closed automatically.
print(f.closed) confirms the file is closed.
Database Connection Management with Context Manager
Let's create a simple database connection management system. The number of database connections that can be opened at a time is also limited(just like file descriptors). Therefore context managers are helpful in managing connections to the database as there could be chances that programmer may forget to close the connection. 

Example:


from pymongo import MongoClient

class MongoDBConnectionManager:
    def __init__(self, hostname, port):
        self.hostname = hostname
        self.port = port
        self.connection = None

    def __enter__(self):
        self.connection = MongoClient(self.hostname, self.port)
        return self.connection

    def __exit__(self, exc_type, exc_value, exc_traceback):
        self.connection.close()

with MongoDBConnectionManager('localhost', 27017) as mongo:
    collection = mongo.SampleDb.test
    data = collection.find_one({'_id': 1})
    print(data.get('name'))
Explanation:

__enter__() opens MongoDB connection.
mongo inside with block is the client object.
You can perform database operations safely.
__exit__() closes the connection automatically.

