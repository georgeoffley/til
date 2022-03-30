# Using Props in React Components

[Source](https://reactjs.org/docs/components-and-props.html)

Props are shorthand for properties. These can be passed into components and be accessible using the object notation.

## Example

```javascript
function Footer(props) {
    return (
        <footer>
            <small>@ 2022 Offley Development. All rights reserved</small>
            <p>This is a prop: {props.name}</p>
        </footer>
    )
}

ReactDOM.render(
    <>
        ...
        ...
        <Footer name="George's Prop" />
    </>,
    document.getElementById("root")
);
```

The above example outlines a component we created using a function component which takes in `props` as an argument. The prop attributes can be used using the object notation, `object.attribute`.

The prop is passed in using the React syntax along with the name of the prop attribute. Similar looking to real HTML.

You can also define a component with props using [ES6 classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) like so:

```javascript
class Footer extends React.Component {
    render() {
        return (
            <footer>
                <small>@ 2022 Offley Development. All rights reserved</small>
                <p>This is a prop: {this.props.name}</p>
            </footer>
        )
    }
}
```

The above would use `this.props.attribute` to reference a passed in prop as the keyword `this` refers to the current class instance.