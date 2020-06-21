## useClickAway.

React hook to detect click or touch events outside an element.

## Installation

```
npm i use-click-away
```

## Usage

```
import {useClickAway} from 'use-click-away';

const [count, setCount] = React.useState(0);
const clickRef = React.useRef('');
useClickAway(clickRef, () => setCount( count + 1)); 

<div ref={clickRef}>
  DOM clicked 0 times!
</div>

```
[![Edit use-click-away](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/use-click-away-0vtmy?fontsize=14&hidenavigation=1&theme=dark)

## Built With

- [React](https://reactjs.org/) - A JavaScript library for building user interfaces

## License

MIT Licensed. Copyright (c) George Bardi 2020.
