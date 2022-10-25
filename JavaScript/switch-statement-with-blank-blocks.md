# Switch statement With Blank Blocks

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)

You know what a switch statement is, a statement which evaluates an expression and allows you to create blocks of logic looking to match the value of the expression.

The thing I found though was the situation where there is a blank block it actually runs the logic of the very next block. See below.

```javascript
const expr = 'Mangoes';
switch (expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Mangoes': // This is the blank block, which will execute the logic in the next block
  case 'Papayas':
    console.log('Something and papayas are $2.79 a pound.');
    // expected output: "Mangoes and papayas are $2.79 a pound."
    break;
  default:
    console.log(`Sorry, we are out of ${expr}.`);
}
```


#JavaScript