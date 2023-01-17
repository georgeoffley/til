# Conditional Rendering in Vue

---
## Docs and Source
[Source Here](https://vuejs.org/guide/essentials/conditional.html#v-if)

---
## Explanation and Notes
You can use the `v-if=""` attribute for HTML elements for conditionally rendering elements. So whatever variable you have set in there will cause the element to render if that variable evaluates as truthy.

[This resource](https://vuejs.org/guide/essentials/conditional.html#v-if) lists the `v-if` and a few other ways to render conditionally.

---
## Code Example
This element will only render if `"awesome"` evaluates as `True`. In this case `"awesome"` is just a string so it will evaluate as `True`.

```JavaScript
<h1 v-if="awesome">Vue is awesome!</h1>
```


#JavaScript 
	#Vue
	