# Record Type in TypeScript

[Source](https://www.typescriptlang.org/docs/handbook/utility-types.html#recordkeys-type)

The record type constructs an object where you can designate the types of the keys and values.

### Example

```javascript
export type Modes = 'a' | 'b';

export type ModeKeys =
  | 'add'
  | 'subtract'

export const MaskModesList: Record<ModeKeys, Modes> = {
  add: 'a',
  subtract: 'b',
};
```

The above does some cool stuff in that we designate the types for the values as a union type in `Modes`. Where the types could be any of the strings given. Same with the `ModeKeys`.

The `ModeKeys` and `Modes` can only be those strings.