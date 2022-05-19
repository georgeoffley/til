# Defining And Passing In Objects In TypeScript Functions

You can define an object and pass that object in as an arg for a TypeScript function.

This is done by defining and object in the function signature. For example

```typescript
function greet(options: { greeting: string; name: string }): string {
  return `${options.greeting}, ${options.name}`;
}
```

Now we have the `options` object defined in our function signature. 

A clean way of calling this function would be

```typescript
const message: string = greet(
  {
    greeting: "Hello",
    name: "George",
  }
);
```

You can also destructure the object being passing in to the function. Like so

```typescript
function greet({ greeting, name }: { greeting: string; name: string }): string {
  return `${greeting}, ${name}`;
}
```