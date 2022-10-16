# Updating State arrays and using `console.log()` to test.

When you use the `useState()` and create a state with an array updating function, keep in mind that the new state updating function runs asynchronously. So the first time you the state is updated any `console.log()` call afterward will run before the state is updated so it will appear as if the first entry into that state was not recorded. 

So maybe, render the state on the page.