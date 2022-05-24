# Closures in JS

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#closures)

Closures are nested functions which give the inner functions access to data in the outer function but encapsulates the inner function and the outer function cannot access the data within the inner function.

```javascript
var pet = function(name) {   // The outer function defines a variable called "name"
  var getName = function() {
    return name;             // The inner function has access to the "name" variable of the outer
                             //function
  }
  return getName;            // Return the inner function, thereby exposing it to outer scopes
}
myPet = pet('Vivie');

myPet();                     // Returns "Vivie"
```