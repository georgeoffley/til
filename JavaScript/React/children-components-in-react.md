# Children Components in React

Children components are components which are nested in parent components. 

Parent components are the top level components which the children are nested in.

## Example

```javascript
function MainContent() {
    return (
        <div>
            <h1>Reasons I'm Excited to Learn React</h1>
            <ol>
                <li>Was first released in 2013</li>
                <li>Was originally created by Jordan Walke</li>
                <li>Has well over 100k stars on GitHub</li>
                <li>Is maintained by Facebook</li>
                <li>Powers thousands of enterprise apps, including mobile apps</li>
            </ol>
        </div>
    )
}

function Page() {
    return (
        <div>
            <MainContent />
        </div>
    )
}

ReactDOM.render(
    <Page />,
    document.getElementById("root")
);
```

The above example outlines a `MainContent` component and a `Page` Component. You can see that the `MainContent` component is nested in the `Page` component. Making the `Page` component a parent to the `MainContent` component.

And to properly order everything you only pass in the `Page` component to the render call. Which will render everything and the code gets to be neat and organized.

#JavaScript
	#React