# Localstorage in Browsers

Source: https://developer.mozilla.org/en-US/docs/Web/API/Window

`localstorage` is a built in propert of the `window` interface.

`localstorage` is kept in the browser and it stores information about the browser window. You can get information like the client computer type, their browser, etc. This also has contains the DOM.

## Retool special note
In Retool, they have a [built in `window.localstorage` interface with the same origin as the standard `window.localstorage`](https://docs.retool.com/docs/share-data-between-apps#:~:text=localStorage is a flexible solution,you need to accomplish this.). This can be used by devs to store information. For example sharing info between apps, etc. For retool's use case that `localstorage` cannot be used outside of retool.

