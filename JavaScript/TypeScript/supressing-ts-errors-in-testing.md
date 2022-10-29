# Suppressing TypeScript Errors in Testing

---
## Docs and Source
[Docs](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-9.html#-ts-expect-error-comments)

---
## Explanation and Notes

When doing things like writing fail condition tests in TypeScript you can use an `// @ts-expect-error` comment before a line to have TypeScript suppress the error.

If there is no error you'll get an error message saying that the comment is not being used.

In the below example I make a function with a type guard (an assert statement checking the type) for the argument to make sure it is a string. However, to test that this fails I need to write a test with the function and a number type passed in. The `// @ts-expect-error` is telling TypeScript to expect and error and suppress the type error.

---
## Code Example

```TypeScript
function doSomething(arg1: string) {
	assert(typeof arg1 === "string");
	// Doing something
}

expect(() => {
	// @ts-expect-error
	soSomething(1);
}).toThrow();
```


#JavaScript 
	#TypeScript 