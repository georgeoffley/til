# Argument Defaults in TypeScript

[Source](https://www.typescripttutorial.net/typescript-tutorial/typescript-default-parameters/)

You can assign parameter (argument) defaults in TypeScript the same way you would in say Python. By setting it to something in the function signature.

So for example

```typescript
function greet(greeting: string; name: string = 'George'): string {
  return `${greeting}, ${name}`;
}

// Returns: Hello, George
```

#JavaScript
	#TypeScript