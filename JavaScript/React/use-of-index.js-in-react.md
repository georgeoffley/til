# Use of Index.js in React

In React, `Index.js` is the actual entry point for the application. 

`App.js` is the main collection of components making up the application.

## Further Notes

```javascript
// App.js

function App() {
  return (
      <Header />
        <App />
      <Footer />
  );
}

export default App;
```

So in the code above you see all the components which make up the entirety of the app are all organized here for us.

```javascript
// Index.js

import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

Here above is where the actual `ReactDOM.render()` function is which renders our application. This is where we import our `<App />` component and do all the rendering. 

#JavaScript
	#React