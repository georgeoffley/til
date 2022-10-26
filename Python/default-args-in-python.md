# Default args in Python

---
## Docs and Source
[Geeks For Geeks Source](https://www.geeksforgeeks.org/default-arguments-in-python/)

---
## Explanation and Notes

You can set the arguments to be a default value in a function. You can also override the value if you want.

---
## Code Example

```Python
def print_def(arg = 'default value'):
	print(f'This is a {arg}')

print_def()
# Prints out "This is a default value"

print_def('something else')
# Prints out "This is a something else"
```


#Python 