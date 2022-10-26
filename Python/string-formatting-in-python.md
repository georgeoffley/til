# String Formatting in Python

---
## Docs and Source
[RealPython Source](https://realpython.com/python-string-formatting/)

---
## Explanation and Notes

Formatting strings in Python is pretty simple. It's just a way to insert Python code into strings to make them more dynamic.

---
## Code Example

```Python
# Old School way of doing string formatting
name = 'George'
string = 'Hello there %s' % name
# => Prints out "Hello there George"

# Slightly newer school way of string formatting
name = 'George'
string = "Hey there {}".format(name)
# => Prints out "Hello there George"

# Current way to to format strings (Python 3.6+)
name = 'George'
string f'Hey there {name}'
# => Prints out "Hello there George"
```


#Python 
