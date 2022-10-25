# Inequality Operator In JavaScript

[Source](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality)

The inequality operator, `!=`, checks whether its two operands are not equal and returns a Boolean.

One note about inequality in JavaScript is that when using the single equal sign, `!=` the process will try to convert the types to match. So for example `3 != "3"` would return false. So in that case JS thinks that the integer three is the same as the string character three.

If you use [strict inequality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality) then JS will also compare types. So `3 !== "3"` would return true.

#JavaScript