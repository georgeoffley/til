# JSDoc notation for types

---
## Docs and Source
[Source Here](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html)

---
## Explanation and Notes
JSDoc annotations allow you to create types for functions, variables, etc., without creating TS files.

The below example shows how to import types and how to annotate basic types.

---
## Code Example

```JavaScript
// Importing Types example
/**
 * @typedef {import('./residents').Resident} Resident
 */

/**

* @type {string}

*/

var s;

/** @type {Window} */

var win;

/** @type {PromiseLike<string>} */

var promisedString;

// You can specify an HTML Element with DOM properties

/** @type {HTMLElement} */

var myElement = document.querySelector(selector);

element.dataset.myData = "";
```


#JavaScript 
	#TypeScript 