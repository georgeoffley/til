# Finding and Object's Properties

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Object/values)

In JavaScript there is a built in function for all objects which returns an array with all the object’s properties. 

### Example

```javascript
const a = {
  id: 1,
  name: "Arthur",
  species: "Aardvark"
};

console.log(Object.values(a));

// Expected Results
// Array [1, "Arthur", "Aardvark"]
```


#JavaScript