# Formatting Datetime in JavaScript

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)

Datetime in JavaScript is fun. You have the ability to create the standard object `Date`. And from there you can extract a useable timestamp string.

## Example

```javascript
function dateFormatter(date: string) {
  // Create date object and construct datetime vars
  const currentdate = new Date(date); 
  const [month, day, year] = [currentdate.getMonth() + 1, currentdate.getDate(), currentdate.getFullYear()]
  const [hour, minute] = [currentdate.getHours(), currentdate.getMinutes()]

  // Format and add in leading zeros
  const datetime = (
    (month < 10 ? "0" + month : month)
    + "/"
    + (day < 10 ? "0" + day : month)
    + "/"
    + year + " "
    + (hour < 10 ? "0" + hour : hour)
    + ":" 
    + (minute < 10 ? "0" + minute : minute)
  )

  return datetime;
}
```

The above takes in a datetime string, creates a `Date` object, extracts the needed variables, and builds a timestamp string. 

#### Notes
The above does not include things like "AM/PM". 


#JavaScript