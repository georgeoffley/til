# Empty Arrays and Objects Falsy in JS

Source: https://www.sitepoint.com/javascript-truthy-falsy/

Empty objects and arrays will return false when evaluated against a true or false.

```javascript
let arr = [];
let obj = {};

if (!arr) { // evaluations as true
  console.log('Nothing Here');
} else {
  console.log('Something here');
}

console.log(arr)

if (!obj) { // evaluations as true
  console.log('Nothing Here');
} else {
  console.log('Something here');
}

console.log(obj)

// Something here
// []
// Something here
// {}
```

The following values are **always falsy**:

- `false`
- `0` (zero)
- `-0` (minus zero)
- `0n` (`BigInt` zero)
- `''`, `""`, ```` (empty string)
- `null`
- `undefined`
- `NaN`

Everything else is **truthy**. That includes:

- `'0'` (a string containing a single zero)
- `'false'` (a string containing the text “false”)
- `[]` (an empty array)
- `{}` (an empty object)
- `function(){}` (an “empty” function)

#JavaScript