# Basic Tailwind Usage

Use spaced out class names when using Tailwind, __NOT COMMA SEPERATED CLASS NAMES LIKE NORMAL CSS CLASSES OR ELSE IT WILL NOT WORK__.

### Example

```javascript
export default function MainContent() {
    return (
        <main className="py-14 px-7">
            <h1 className="text-4xl font-bold text-white">Fun Facts About React</h1>
            ...
        </main>
    )
}
```

From the above `py-14` is space separated from `px-7`.