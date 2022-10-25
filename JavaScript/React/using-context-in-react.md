# Using Context in React

[Source](https://beta.reactjs.org/learn/passing-data-deeply-with-context)

Context in react is a way to pass data to components. Different from using props, context gives us the ability to pass data deeply into components.

It also helps when data is needed by multiple sibling components. Using props you need to pass the data to each sibling. You can clean this up using context. 

Context is designed to share data that can be considered "global" for a tree of React components.

## Example

Using props you might have a layout such as below.

```javascript
class App extends React.Component {
  render() {
    return <Toolbar theme="dark" />;
  }
}

function Toolbar(props) {
  return (
    <div>
      <ThemedButton theme={props.theme} />
    </div>
  );
}

class ThemedButton extends React.Component {
  render() {
    return <Button theme={this.props.theme} />;
  }
}
```

In the above example the `Toolbar` component must pass the theme prop to the `ThemedButton` component. This can get messy quickly if you need to pass this prop to multiple buttons.

Below is the example with context used.

```javascript
const ThemeContext = React.createContext('light');

class App extends React.Component {
  render() {
    return (
      <ThemeContext.Provider value="dark">
        <Toolbar />
      </ThemeContext.Provider>
    );
  }
}

function Toolbar() {
  return (
    <div>
      <ThemedButton />
    </div>
  );
}

class ThemedButton extends React.Component {
  static contextType = ThemeContext;
  render() {
    return <Button theme={this.context} />;
  }
}
```

In the above example we use the `createContext` React hook to create an instance of our needed context. Now the `Toolbar` component does not need to pass in the theme prop. We are able to use our context to get the data in the `ThemedButton` component.

- `useContext` - Accepts a context object (value from `createContext` hook) and returns the current context value for that context.
- `createContext` - Created a context object. React will read the current context matching the `Provider` above it in the tree when rendering.
#JavaScript
	#React