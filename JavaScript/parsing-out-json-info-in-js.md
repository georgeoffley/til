# Parsing Out JSON data in JSON

```javascript
// Store JSON data in a JS variable
var json = '{"name": "Peter", "age": 22, "country": "United States"}';

// Converting JSON-encoded string to JS object
var obj = JSON.parse(json);

// Accessing individual value from JS object
alert(obj.name); // Outputs: Peter
alert(obj.age); // Outputs: 22
alert(obj.country); // Outputs: United States
```