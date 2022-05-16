# Generics For Functions

Sources
- [TS Docs](https://www.typescriptlang.org/docs/handbook/2/generics.html)
- [Antonin Januska's Video Explainer](https://youtu.be/nZ89NCR6-Us)

Generics are stand ins used for representing other types of data being passed through a function. 

### Functions

Generics can be used for functions. It is great for type hinting and type safety.

They allow you to pass in generic args and also have generic return types. 

Great for working with data where the type returned might not be known.

```typescript
interface User {
  id: number,
  name: string
}

async function getResource<T>(modelType: string) {
  let resp = await fetch(`/api/${modelType}`);
  let json = await resp.json();

  return json as T[];
}

getResource<User>('user')
  .then((users) => {
    users.map(user => {
      // Code to do something with object members
      // You can now have access to something like user.id in autocomplete 
      // and also TS won't throw an error
    })
  });
  ```

In the above we have a standard interface with an ID and Name.

We use a generic `<T>` since we do not know what we'll get back and we want ot be able to use this for model object.

Using a generic will give us the flexibility to use this with other resourcesm but still have access to the underlying properties for type hinting and auto completion. 