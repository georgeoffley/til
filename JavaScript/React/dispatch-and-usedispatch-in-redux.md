# `dispatch` and `useDispatch` in Redux

Source: https://react-redux.js.org/using-react-redux/connect-mapdispatch#approaches-for-dispatching

Redux is a big ole immutable object which we store information about an app's state.

Think of it almost like a big client side DB.

Since that big ole object is immutable we need something that allows us to mutate the app. This is done using dispatching. Dispatching is the act of calling a function with arguments that changes stuff in the redux store.

So someone might make a dispatch object like this:

```javascript
const dispatch = useDispatch();
```

This is using a home spun hook. Generally, you would call the dispatch function using `store.dispatch()` as `dispatch()` is a built in function. 