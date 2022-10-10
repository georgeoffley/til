# Using `Promise.all()` for concurreny in JavaScript

Resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all

The `Promise.all()` function is a built in function for a promise object. It takes in an iterable of Promise objects and fullfills them all concurrently.

The function returns all the fullfilled promises at once. 

The returned promise is fulfilled with an array containing all the values from the promises.

Here is an example:

```javascript
async function main() {

    // Look into data-store dir and get file names
    const dataStoreFiles = await promisFunction(args);

    // Open all the files and add the Promises objects to an array
    const recordDataPromiseArr = [];
    for (const fileName of dataStoreFiles) {
        recordDataPromiseArr.push(openFile('file_url'))
    }

    // Concurrently fullfill all the promises and create migration file
    Promise.all(recordDataPromiseArr).then((data) => {
        // Combine records that meet our requirements
        const combinedRecords = recordSift(data);

        // Write records marked for migration
        fileWriter(
            'new_path',
            JSON.stringify(combinedRecords, null, 2)
        )
    })
}
```

If one of the promises rejects it will add in the value of the rejection into the array position regardless of if the other promises reject or not.