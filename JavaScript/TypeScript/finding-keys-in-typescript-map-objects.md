# Finding Keys In TypeScript Map Objects

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/has)

You can use the `has()` method to find keys in a map object.

The method will return a boolean `true` if the object has the specified key, and false if not.

### Example

```javascript
let numbers = new Map<number, number>();

numbers.set(15, 46);

numbers.has(15); // Returns true
numbers.has(22); // Returns false
```

#JavaScript
	#TypeScript