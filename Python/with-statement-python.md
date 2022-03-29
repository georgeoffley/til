# With Statement in Python

[Source](https://realpython.com/python-with-statement/)

The With statement in Python is a standard way to handle exceptions and interact with different resources such as DB connection, files, etc..

## Example

```python
with open('file', 'w') as file:
    file.write('hello world')
```

The with statement utilizes the context protocols to create a context for handling streams of data.

This is no need to call close as the `file` class has built in constructors and destructors for handling the file stream. The required built in functions are `__enter__()` and `__exit__()`

## Custom Functions

You can also make custom functions which are able to utilize with statements. 

```python
class FileWriter:
    def __init__(self, file_name):
        self.file_name = file_name

    def __enter__(self):
        self.file = open(self.file_name, 'w')
        return self.file

    def __exit__(self, exc_type, exc_val, exc_tb):
        if exc_type is None:
            print("Normal Exit: File Written\n")
        else:
            print(f"Exception Detected on Exit")
            print(f"Exception Type: {exc_type}")
            print(f"Exception Value: {exc_val}\nException Traceback: {exc_tb}\n")

        self.file.close()
```

The above function defines the `FileWriter` function and also creates the `__enter__()` and `__exit__()` functions that have construction logic and deconstruction logic.