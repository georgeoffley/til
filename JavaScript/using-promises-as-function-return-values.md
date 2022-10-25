# Using Promises as Function Return Values

When looking through Promise tutorials you usually see something like this:

```javascript
async function PromiseFunc(args) {
    try {
        const data = async fetch('api_url');
        console.log(data);
    } catch (error) {
        console.log(error)
    }
}
```

It makes no sense, since you don't make stuff to print to a console. This gives me no idea how to make this repeatable and useable. 

If I wanted to create a reusable function I would want to do something like this:

```javascript
// promiseFunc.js
export async function promiseFunc() {
    try {
        const data = async fetch('api_url');
        return data;
    } catch (error) {
        console.log(error)
    }
}

// mainFunc.js
async function mainFunc(args) {
    const apiData = await promiseFunc();

    // See data
    apiData.then((data) {
        // This gives us access to our data
        ...
    })
}
```

When you return a promise object from a function, you get a `Promise<pending>` since the function has no fulfilled the promise. 

You need to use an `await` keyword and save it to a variable. 

Then you need to use a `.then()` chain with the returned `data` argument which is your fullfilled promise (your data).

#JavaScript