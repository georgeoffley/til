# Arbitrary Arguments in Python

---
## Docs and Source
[Online Source](https://www.toppr.com/guides/python-guide/references/methods-and-functions/function-argument/python-function-arguments-default-keyword-arbitrary/#:~:text=follows%20keyword%20argument-,Python%20Arbitrary%20Arguments%20%E2%80%93,the%20parameter%20in%20the%20function.)

---
## Explanation and Notes

For creating methods and functions with arguments where you might not know how many arguments will be passed in.

Arbitrary arguments are accessible using array syntax (`name[0]`). 

There are also kwargs which are keyed arguments. This gives you the ability to have keys to your argument values.

---
## Code Example

```Python
def print_stuff(*args):
	for i in args:
		print(i)

print_stuff([1,2,3])
# => Prints out 1,2,3

def print_names(**kwargs):
	for key, val in kwargs.items():
		print(f'Key: {key}, Val: {val}')

print_names(first="George", last="Offley")
# => prints
# "Key: first, Val: George"
# "Key: last, Val: Offley"
```


#Python 