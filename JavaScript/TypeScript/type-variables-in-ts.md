# Type Variables in TypeScript

[Source](https://www.typescriptlang.org/docs/handbook/2/generics.html#hello-world-of-generics)

In TypeScript you have the ability to pass in generics as stand ins for other types. So for example

```typescript
function identity<Type>(arg: Type): Type {
  return arg;
}
```

The `identity` function will take in the special generic variable, denoted using the `<>` angle brackets, and that will serve as a stand in for other types you pass in. 

For example 

```typescript
let output = identity("this is an output string");

console.log("Type ID function return: " + output);
```

The `output` variable will use the function and pass in a string. The compiler will look at this string and infer the string argument's type as type to be returned. 

Alternatively you can write the above like:

```typescript
let output = identity<string>("This is a string return");
```

Which explicitely passes in the return type using the `<>` angle brackets. The first solution is cleaner but for more complicated cases this might be better to go with.

#JavaScript
	#TypeScript