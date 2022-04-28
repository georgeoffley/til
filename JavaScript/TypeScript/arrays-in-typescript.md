# Arrays in TypeScript

[Source](https://www.tutorialsteacher.com/typescript/typescript-array)

You can declare arrays in TypeScript using the below methods.

```javascript
let numbers: number[] = [];
```

Or you could do this

```javascript
let moreNumbers: Array<number>;
moreNumbers = [];
```

In the second example, you have to make sure you assign it after you declare it before using the array. By assign I mean the second line, `moreNumbers = []`. You need to assign a value before you begin manipulating the array.

Also remember, if you are using `const` like this.

```javascript
const moreNumbers: Array<number> = [];
```

You need to make sure you're assigning the value in the first line. Like we have it above.