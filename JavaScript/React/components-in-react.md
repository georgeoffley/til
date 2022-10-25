# Components in React

Components in React are JavaScript functions that we can use to write JSX and easily add them to our pages.

Using components makes React apps [composable](https://en.wikipedia.org/wiki/Composability) which lets us separate our concerns and be able to easily make changes to components without effecting the entire application.

## Example

Using components lets us create small bit of the site and assemble them together. For example below is a header and a footer component.

```javascript
function Header() {
    return (
        <header>
            <h1>Reasons I'm Excited to Learn React</h1>
            <nav>
                <img src="./react-logo.png" width="80px" />
            </nav>
        </header>
    )
}

function Footer() {
    return (
        <footer>
            <small>@ 2022 Offley Development. All rights reserved</small>
        </footer>
    )
}
```

After that we can create a page component

```javascript
function Page() {
    return (
        <ul>
            <li>Was first released in 2013</li>
            <li>Was originally created by Jordan Walke</li>
            <li>Has well over 100k stars on GitHub</li>
            <li>Is maintained by Facebook</li>
            <li>Powers thousands of enterprise apps, including mobile apps</li>
        </ul>
    )
}
```

Finally, we can assemble them in a React app using the `<>` syntax. Similar to HTML. The brackets will "call" an instance of our components

```javascript
ReactDOM.render(
    <>
        <Header />
        <Page />
        <Footer />
    </>,
    document.getElementById("root")
);
```

#JavaScript
	#React