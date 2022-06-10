# Conforming Types to Specific Values

We can make types which only have a preassigned value in them.

### Example

```javascript
type Mode = 'a' | 'b';
```

So in the above we have two things happening. We have a union type which could be either `'a'` or `'b'`. This also means that the type `Mode` can only have a value of `'a'` or `'b'` or TypeScript will throw an error.