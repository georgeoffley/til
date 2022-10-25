# Fragments in React

[Source](https://reactjs.org/docs/fragments.html)

Fragments in React act as parent elements in JSX for rendering sibling elements.

When writing JSX we need the elements to be nested under a single parent. You cannot have two sibling elements without them being nested and acting as children elements.

## Example

```javascript
const page = (
    <>
        <h1>Hello</h1>
        <p>This is my page</p>
    </>
);
```

The above is the shorthand fragment syntax. The Long form alternative looks like this:

```javascript
const page = (
    <React.Fragment>
        <h1>Hello</h1>
        <p>This is my page</p>
    </React.Fragment>
);
```

The above shows the blank fragment syntax which can act as a parent element without adding anymore elements into our page.

Another alternative is using a `<div>` to nest the elements but this can create problems of our own as you now have an extra `<div>` element.

#JavaScript
	#React