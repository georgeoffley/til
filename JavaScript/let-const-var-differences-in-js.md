# Let/Const/Var Differences And Use In JavaScript

[Source](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference/)

## Var

`Var` is the original way of declaring variables. Since ES6 came out everything's changed but you can still use `var`. 

`Var` is globally scoped when outside of a function, but functionally scoped inside of a function.

```javascript
var greeter = "hey hi"; // Global Scoped

function newFunction() {
    var hello = "hello"; // Function scoped
}
```
You can also redeclare `var` and also overwrite it. This can become a problem if we were to use `greeter` in other parts of our code without intention.

## Let

Let is the new and preferred way to declare variables.

Let is block scoped, in that the scope exists within curly braces, `{}`.

```javascript
let greeting = "say Hi";
let times = 4;

if (times > 3) {
    let hello = "say Hello instead";
    console.log(hello);// "say Hello instead"
}
console.log(hello) // hello is not defined
```

Let can also not be redeclared, but it can be overwritten. This helps as we have a mutable variable but we won't run into issues redeclaring later in our code, as it will just error out.

## Const

`Const` is similar to `let`, but the values will remain constant.

`Const` is also block scoped.

`Const` also cannot be redeclared, but it also cannot be overwritten. However, if we create an object using a `const` we can update it's properties.

```javascript
const greeting = {
    message: "say Hi",
    times: 4
}

// Can be updated using
greeting.message = "say Hello instead";
```