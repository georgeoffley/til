# Spread Operator in JavaScript

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

The spread operator, `...`, in JavaScript is an operator used with an iterable object such as an array expression or string can be expanded where one or more elements are expect.

A little similiar to the [`map()`](https://www.geeksforgeeks.org/python-map-function/) or [list copmprehension](https://realpython.com/list-comprehension-python/) in Python.

### Example

```javascript
let numbers = [1,2,3];

console.log(...numbers);
// prints: 1,  2,  3
```

Another Example

```javascript
const users: User[] = [];

let james: User = {
  name: 'James',
  id: 1
};

let jimbo: User = {
  name: 'Jimbo',
  id: 2
};

users.push(james);
users.push(jimbo);

console.log(...users);

//prints: 
// {
//   "name": "James",
//   "id": 1
// },  {
//   "name": "Jimbo",
//   "id": 2
// } 
```


#JavaScript