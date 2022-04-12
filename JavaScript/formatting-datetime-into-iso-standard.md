# Formatting Datetime into ISO Formats

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toISOString)

The [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format is a standard format for datetime strings. You can easily convert a [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) object into a string print out of the datetime in this formation in JavaScript.

## Example

```javascript
const event = new Date('05 October 2011 14:48 UTC');
console.log(event.toString());
// expected output: Wed Oct 05 2011 16:48:00 GMT+0200 (CEST)
// (note: your timezone may vary)

console.log(event.toISOString());
// expected output: 2011-10-05T14:48:00.000Z
```

Above you can see that you create a new date object and the `toISOString()` function is a built in class function for the date object.