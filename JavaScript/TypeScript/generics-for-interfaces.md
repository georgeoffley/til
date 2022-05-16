# Generics For Interfaces

Sources
- [TS Docs](https://www.typescriptlang.org/docs/handbook/2/generics.html)
- [Antonin Januska's Video Explainer](https://youtu.be/nZ89NCR6-Us)

Generics are stand ins used for representing other types of data being passed through an interface or through a function. 

### Interfaces

Generics can be used for interfaces. It is great for type hinting and type safety.

```typescript
interface Model<T> {
    id: number;
    value: T;
}

let newModel: Model<string> = { id: 1, value: 'Brenda' };

console.log(newModel);
// [LOG]: {
//   "id": 1,
//   "value": "Brenda"
// } 
```
The above creates a Model interface which uses a generic for the value type. 

We can take advantage of this when we create new instances of this interface by using `Model<string>`. In the above case a string.

