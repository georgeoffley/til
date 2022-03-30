# Rendering JSX Using ReactDOM

[Source](https://reactjs.org/docs/react-dom.html#render)

ReactDOM is a React library that gives us access to the DOM. We can use the `render()` function to actually show things on a webpage.

## Example

This is an example of [JSX](https://reactjs.org/docs/introducing-jsx.html). Which is the syntax used in react to create HTML. The syntax looks similiar to HTML.

```JavaScript
const page = (
    <div>
        <img src="./react-logo.png" width="40px" />
        <h1>Fun Facts about React</h1>
        <ul>
            <li>Was first released in 2013</li>
            <li>Was originally created by Jordan Walke</li>
            <li>Has well over 100k stars on GitHub</li>
            <li>Is maintained by Facebook</li>
            <li>Powers thousands of enterprise apps, including mobile apps</li>
        </ul>
    </div>
);
```

 __You should note__ that the above object will only return a JavaScript object, not pure HTML. We need the help of React to get it to render on the page.

```javascript
ReactDOM.render(
    page,
    document.getElementById("root")
);
```

The above snippet will take in our `page` object, and the HTML selector as arguments, and use the `page` object to render HTML on the selector argument.

