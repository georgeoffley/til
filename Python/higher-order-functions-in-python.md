# Higher Order Functions In Python

[Source](https://www.geeksforgeeks.org/higher-order-functions-in-python/)

A higher order function is a function that can take functions as parameters and returns a function.

Decorators are used as an easy way to reference higher order functions.

## Example

```python
def create_adder(x): 
    def adder(y): 
        return x + y 
    
    return adder 
    
add_15 = create_adder(15) 
    
print(add_15(10))

# Returns
=> 25
```

