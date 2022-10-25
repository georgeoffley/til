# This Keyword

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

In most cases, `this` can be used to return a property of a function or class instance.

So an example would be below.

```javascript
const test = {
  prop: 42,
  func: function() {
    return this.prop;
  },
};

console.log(test.func());
// expected output: 42
```


#JavaScript