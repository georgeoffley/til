# Async Await

Sources
- [JS Info](https://javascript.info/async-await)
- [James Q Quick's Video](https://youtu.be/670f71LTWpM)

An evolution on [Promises](promises.md) is the `await` and `async` syntax. These allwo you to write and consume process a little easier than using the base syntax.

Now instead of writing out the promises like referenced in the [promises](promises.md) note we can write the following:

```javascript
import fetch from 'node-fetch';

const fetchPokes = async (id) => {
  try {
    const res = await fetch(`https://pokeapi.co/api/v2/pokemon/${id}`);
    const data = await res.json();
    console.log(data);
  } catch (err) {
    console.error(err);
  }
};

fetchPokes(1);
```

In the above example, we're prepending the function signature with the keyword `async`, adding in the `await` keyword at the front of the variable assignment, and then wrapping those in a `try/catch` statement.

### `Async`

Async is a special keyword in JS which you put before the function. This will make the function always return a promise object. Anything in that block is also wrapped in a resolved promise automatically.

### `Await`

`Await` is only valid inside an `async` function. This keyword makes JS wait until that promise finishes and returns the result. 

The function execution pauses on the line with an `await`. It only restarts when the result object comes back. This does not cost CPU cycles as JS can do other things while this waits for the response back.

`Await` can __only__ be used in an `async` function and will throw and error if applied anywhere else.