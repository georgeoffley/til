# Wrapper Components in React Using Props

[Source](https://youtu.be/LME0Uv9SlDA)

You can create components which serve as wrapper components for passing around props and their children.

## Example

```javascript
// Wrapper.js

export default function Wrapper(props){
    return (
        <div>{props.children}</div>
    )
}
```

```javascript
// App.js
import Wrapper from "./Components/Wrapper"

function App() {
    return (
        <div>
            <Wrapper>
                <p>Child P</p>
            </Wrapper>
        </div>
    )
}
```

The wrapper function takes in props and can print the `props.children` attribute from the `props` object.