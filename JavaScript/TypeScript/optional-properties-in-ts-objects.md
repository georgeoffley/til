# Optional Properties in TS objects

[Source](https://www.becomebetterprogrammer.com/typescript-question-mark/#:~:text=More%20About%20TypeScript%3F-,What%20does%20%3F%3A%20mean%20in%20TypeScript%3F,its%20value%20can%20be%20undefined%20.)

When creating objects in TS you can set properties to be optional properties. 

So if you have an object which might have or might not have a property, for example a middle name in a user object, you can make one of the properties optional using the `?` operator in the key decalration. 

### Example

```typescript
interface User {
	id: string;
  firstName: string;
  middleName?: string;
  lastName: string;
}

const admin: User = {
  id: "123",
  firstName: "Foo",
  lastName: "Bar",
};

console.log(admin);

// Prints
{
  firstName: "Foo",
  id: "123",
  lastName: "Bar"
}
```