# `For Of` Loops

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

The `for of` loop which loops through and iterable but creates a new variable for you to have access to the value.

It's essentually a `foreach` loop. For example:

```javascript
const arr1 = [1,2,3];

for (let num of arr1) {
	console.log(num);
}

// Expected output:
// 1
// 2
// 3
```

You can also use this to loop through a map like so:

```javascript
const iterable = new Map([['a', 1], ['b', 2], ['c', 3]]);

for (const entry of iterable) {
  console.log(entry);
}
// ['a', 1]
// ['b', 2]
// ['c', 3]

for (const [key, value] of iterable) {
  console.log(value);
}
// 1
// 2
// 3
```


#JavaScript