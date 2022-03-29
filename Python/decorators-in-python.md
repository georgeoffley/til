# Decorators in Python

A decorator in Python is syntactical sugar to reference functions that take in functions as arguments and returns those functions. 

[Source](https://realpython.com/primer-on-python-decorators/)

## Example

```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called")
        func()
        print("Something is happening after the function is called")
    return wrapper

@my_decorator
def say_whee():
    print("Whee!")
```

Referencing the `say_whee` function yields:

```bash
>>> say_whee()
Something is happening before the function is called
Whee!
Something is happening after the function is called
```

The `@` symbol, sometimes called pi syntax, gives us an easy way to run wrapper functions.

