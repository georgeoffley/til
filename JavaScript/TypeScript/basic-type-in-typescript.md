# Basic Type In TypeScript

The fundemental thing about TS is that it uses types to check our work. 

Here is a basic type for a `Hello World` function.

```typescript
type Salutation = {
  greeting: string;
  name: string;
};
```

We can use that as such

```typescript
function greet({ greeting, name }: Salutation): string {
  return `${greeting}, ${name}`;
}
```

#JavaScript
	#TypeScript