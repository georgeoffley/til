# Prop Defaults

You can create some code where props are able to be passed in with defaults if not provided. 

```typescript
// RoundedImg.tsx
const RoundedImg = (props: ImgProps) => {
  return (
    <img
      src={props.src}
      style={{ borderRadius: props.borderRadius }}
      className="round-img"
    />
  );
};

RoundedImg.defaultProps = {
  borderRadius: "50%"
};

// App.tsx
export default function App() {
  return (
    <div>
      <RoundedImg src="https://picsum.photos/id/237/300/300" />
    </div>
  );
}
```

I was also able to accomplish this in the function call for the `RoundedImg` component.

```typescript
const RoundedImg = ({ src, borderRadius = "50%" }: ImgProps) => {
    ///
};
```

#JavaScript
	#React