# Filtering Arrays in JS

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

In JS there is a built in function for arrays called `.filter()` which takes the given array and returns a new array with all the values which match the arguments in the function. 

### Example

```javascript
const someStuff = [1,2,3,4,5];

const filteredStuff = someStuff.filter(
  (val) => val > 3,
);

console.log(filteredStuff);

// Expected results
// > Array [4, 5]
```


#JavaScript