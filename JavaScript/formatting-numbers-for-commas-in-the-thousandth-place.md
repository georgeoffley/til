# Formatting Nyumbers for Commas in the Thousandth Place

```javascript
var numberFormatter = Intl.NumberFormat('en-US');
var data = data.totalusers[0];
return numberFormatter.format(data);
```

However, this [resource](https://www.codingem.com/comma-thousand-separator-in-javascript/#:~:text=To%20comma%2Dseparate%20thousands%20in,the%20number%20to%20the%20USA.) makes it easier using the toLocaleString('en-US') but this did not work in Retool

#JavaScript