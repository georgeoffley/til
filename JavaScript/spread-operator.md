# Spread Operator in JavaScript

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

The spread operator, `...`, in JavaScript is an operator used with an iterable object such as an array expression or string can be expanded where one or more elements are expect.

A little similiar to the [`map()`](https://www.geeksforgeeks.org/python-map-function/) or [list copmprehension](https://realpython.com/list-comprehension-python/) in Python.

### Example

```javascript
function sum(x, y, z) {
  return x + y + z;
}

const numbers = [1, 2, 3];

console.log(sum(...numbers));
// expected output: 6

console.log(sum.apply(null, numbers));
// expected output: 6
```