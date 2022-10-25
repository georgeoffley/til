# Promises

Sources
- [James Q Quick's Video](https://youtu.be/670f71LTWpM)
- [JS Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)

A Promise is a JS object which represents the eventual completion or failure of an async operation and resulting value.

These run off the idea of error first callbacks, or just error handling. 

Here is a basic example of a Promise object being created.

```javascript
// promises
const myPromise = new Promise((resolve, reject) => {
    const rand = Math.floor(Math.random() * 2);
    if(rand == 0) {
        resolve();
    } else {
        reject();
    }
});

myPromise
    .then(() => console.log('Success'))
    .catch(() => console.log('Fail'));
```

The above is a simple random number checker looking for the number `0`.

Promises, as they are created above, take in a `resolve` and a `reject` callback function and runs the `resolve` on a success and the `reject` on a fail. 

We can then consume this Promise object by running the function and then calling the built in `.then()` and `.catch()` functions for a promise object.

### `.then`

The `.then` is a built in promise object function used for consuming a success when a Promise is called. 

### `.catch`

The `.catch` is a built in promise object function used for consuming a fail when a promis is called. 

### Chaining

The way you see these written above:

```javascript
myPromise
    .then(() => console.log('Success'))
    .catch(() => console.log('Fail'));
```

is called chaining, and it's a little cleaner to read. You can continually chain these together as well. 

A better example:

```javascript
import fetch from 'node-fetch';

fetch('https://pokeapi.co/api/v2/pokemon/ditto')
    .then((res) => res.json())
    .then((data) => console.log(data))
    .catch((err) => console.error(err));
```

In the above case we get the response promise object, `res`, convert it to JSON using the `.json()` function, then chain another `.then` which takes in the `data` and then logs that for us.

#JavaScript