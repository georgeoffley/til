# Async Await Vs Promises

Good resources for the difference:
- [https://youtu.be/670f71LTWpM](https://youtu.be/670f71LTWpM)
- [https://youtu.be/_9vgd9XKlDQ](https://youtu.be/_9vgd9XKlDQ)

Promises return promise objects which can be chained using `.then()` and `.catch()`

Promises can return a promise object which calls a `resolve()` callback or a `reject()` callback. Which can be used to grab your data.

### Promise

```javascript
// This is a functioning query triggering using promises
const userSearch = await new Promise((resolve) =>{
  // I am doing this in retool but it would work similiarly using a fetch() command
  // For example: const response = await fetch('https://graphql-pokemon2.vercel.app/')
  query1.trigger({
    onSuccess:(data) => {
      resolve(data);
    },
  });
});

// Returns the query data
return userSearch
```
Using `async` functions with the `await` keyword cleans this up a little.

When using `async` with `await` we are returning a promise object that has either already run the `resolve()` callback or the `reject()` callback. So we don’t need to call them ourselves. 

```javascript
// This also works
const userSearch = async () => {
  try {
    const data = await query1.trigger({
      additionalScope: {
        user_name: 'George Offley'
      },
    });
		// We can return the data variable since if that return is called
		// that means the promise did not error, and we can return data
		// DOES NOT MEAN THE DATA THAT IS RETURNED IS THE DATA YOU NEED
    return data;
  } catch (error) {
		// 
    return error;
  }
}

// Returns the query data
return userSearch
```