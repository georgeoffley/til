# Computed Keys in JS

Good Resource

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer#syntax

You can make object keys dynamic using `[]`

Example:

```javascript
const prop = 'foo';

o = {
	[prop]: 'hello',
}
// Evaluateds to {'foo':'hello'}
```