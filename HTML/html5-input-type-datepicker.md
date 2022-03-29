# HTML5 Input Type For Datetime Picker
---

[Source](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local)

The HTML5 spec is able to pickup on input types and create widgets which allow for easy user interaction.

One of those inputs is type `datetime-local` which creates a datetime picker. The compatible browser looks at the input and if an available type is defined in the `type` attribute the browser can create the widget.

## Example

```Javascript
export const DateTimeInputWidget: React.FC<RowEditWidgetProps> = ({
  currentData,
  updateField,
}) => (
  <input
    className={
      "border-0 h-full pl-1 text-base placeholder-gray-600 text-gray-700 bg-transparent"
    }
    type="datetime-local"
    name="dateTime"
    value={currentData.dateTime}
    onChange={event => {
      updateField(event.target.value);
    }}
  />
);
```

The above outlines a React component, which utilizes HTML5's input tag to create a date picker widget.

Also offers events such as `change` and `input`.

Gracefully downgrades to a textbox when not compatible.