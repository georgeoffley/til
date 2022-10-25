# `useCallback` in React

Source: https://reactjs.org/docs/hooks-reference.html#usecallback

This hook returns a [memoized](https://en.wikipedia.org/wiki/Memoization) callback. A callback is a function that is called by another function.

Memoization is an optimization technique where you store the results of expensive function calls and returns the cached results when the same inputs are passed in.

`useCallack` does the same thing. When named dependancies are passed in the only time the function will run again is when the passed in deps change. Until then we get the cached results.

Below is an example from the docs.

```javascript
const memoizedCallback = useCallback(
  () => {
    doSomething(a, b);
  },
  [a, b], // <= won't run again unless these deps are changed
);
```

#JavaScript
	#React