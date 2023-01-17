# `Mounted()` hook in Vue

---
## Docs and Source
[Source Here](https://masteringjs.io/tutorials/vue/mounted)

---
## Explanation and Notes
The `mounted()` function is a lifecycle hook for rendering stuff.

Much like other frameworks like React, Vue has lifecycle events for each component, and we can use hooks to override the behavior of those lifecycle stages. 

Below is an example of this where we make an HTTP request when the component is mounted.

[Here is more information about the Vue component lifecycle.](https://vuejs.org/guide/essentials/lifecycle.html#lifecycle-diagram)


---
## Code Example

```JavaScript
const url = 'https://jsonplaceholder.typicode.com/users/1';

const app = new Vue({
  data: () => ({ user: null, error: null }),
  // Display username if available, and error message if not
  template: `
    <div>
      <div v-if="user != null">
        {{user.name}}
      </div>
      <div v-if="error != null">
        {{error.message}}
      </div>
    </div>
  `,
  mounted
});

async function mounted() {
  try {
    this.user = await axios.get(url).then(res => res.data);
    this.error = null;
  } catch (error) {
    this.user = null;
    this.error = error;
  }
}
```


#JavaScript 
	#Vue 