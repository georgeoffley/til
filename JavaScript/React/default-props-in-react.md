# Default Props in React

You can set default props for components in react.


In the case where someone might not pass in all the props needed, a default will stave off and error and keep required default values.

Here is an example.

```javascript
export const Card = (props) => {
	const styles = {
        backgroundColor: props.cardColor,
        height: 100,
        width: 100
    };

	return (
        <div style={styles}></div>
    );
};

Card.defaultProps = {
	cardColor: "blue";
};
```

Here is an example of doing this using class components.

```javascript
class Card extends React.Component {
    static defaultProps = {
        cardColor: "blue",
        height: 100,
        width: 100
    }
    
    render() {
        const styles = {
            backgroundColor: this.props.cardColor,
            height: this.props.height,
            width: this.props.width
        }
        
        return (
            <div style={styles}></div>
        )
    }
}
```

#JavaScript
	#React