# React hook to detect click or touch events

`useClickAway()` reacts to clicks outside the bound element, and calls the expression that is passed in when this event is detected.

Suppose you're working on a Modal component that renders a dialog box, and you wish to close the modal if the user clicks away this is the ideal scenario for `useClickAway()` custom hook.

## Installation

Using `npm`:

```bash
npm i use-click-away --save
```

## Usage

Import the hook:

```javascript
import { useClickAway } from "use-click-away";
```

### Full example

```
export default () => {
  const [modal, setModal] = React.useState(false);
  const clickRef = React.useRef("");

  useClickAway(clickRef, () => {
    setModal(false);
  });

  return (
    <div className="container">
      <button onClick={() => setModal(true)}>Show Modal</button>
      {modal && <div ref={clickRef} className="modal">Modal Content</div>}
    </div>
  );
}

```

## Specification

### `useClickAway()` input

- `clickRef: element` - The dom element to bind our hook.
- `callback: function` - The callback that runs after user click

## Built With

[React](https://reactjs.org/)

## License

[MIT](./LICENSE.md)
