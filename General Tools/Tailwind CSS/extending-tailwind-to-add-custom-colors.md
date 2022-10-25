# Extending Tailwind Add Custom Colors

[Source](https://tailwindcss.com/docs/customizing-colors)

If tailwind does not have the colors or anything else you need you can add custom colors into your Tailwind configuration.

### Examples

Your `tailwind.config.js` file should look like this if you are looking to add additional colors.

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        'white' : '#FFFFFF',
      }
    },
  },
}
```

You have to make sure you nest the `colors` block in the `extend` block which will allow you to use all the default colors that come with tailwind in a addition to your custom stuff.

If you need to use all custom colors and not use the colors included in Tailwind you can setup the `tailwind.config.js` like so:


```javascript
module.exports = {
  theme: {
    colors: {
      transparent: 'transparent',
      current: 'currentColor',
      'white': '#ffffff',
    },
  },
}
```

### Using the Colors

Using the custom colors is as simple as adding in the literal name. So going off the example above to change the colors of the text you'd use `text-white` for a class name. Same for say the background, which would be `bg-white`.

#GeneralTools 
	#TailWindCss 