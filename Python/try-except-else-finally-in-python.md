# Try, Except, Else, Finally in Python

The try statement's full use includes the `Try`, `Except`, `Else`, and `Finally` keywords.

These are great for flow control as they not only give you the ability to control how to handle exceptions but also to control what happens after to more gracefully degrade after an exception is thrown.

## Example

```python
try:
    age = int(input('Enter Age: '))
except:
    print('Invalid value')
else:
    print(f'Here is your age: {age}')
finally:
    print('Act like it!')
```

- `Try` is for running the conditional which may throw an error.
- `Except` is for catching the errors, and controlling the response.
- `Else` will run if there was no error.
- `Finally` runs after all the other code blocks have run,

#Python