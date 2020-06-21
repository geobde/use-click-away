## useClickAway.

React hook to detect click or touch events outside an element.

![Alt text](https://github.com/geobde/use-click-away/blob/master/animation.gif "Search")

## Installation

```
npm i use-click-away
```

## Usage

### Modal Example

```
import React from "react";
import { useClickAway } from "use-click-away";

export default () => {
  const [modal, setModal] = React.useState(false);

  const onClickOutside = () => {
    setModal(false);
  };
  return (
    <div className="container">
      <button onClick={() => setModal(true)}>Show Property</button>
      <Modal
        modal={modal}
        setModal={setModal}
        onClickOutside={onClickOutside}
      />
    </div>
  );
};

const Modal = ({ modal, setModal, onClickOutside }) => {
  const clickRef = React.useRef("");
  useClickAway(clickRef, onClickOutside);

  return (
    modal && (
      <div className="shadow">
        <div ref={clickRef} className="modal">
          <iframe
            width="800"
            height="600"
            frameborder="0"
            scrolling="no"
            marginheight="0"
            marginwidth="0"
            src="https://www.openstreetmap.org/export/embed.html?bbox=-74.00082707405092%2C40.73125075736151%2C-73.99181485176088%2C40.73703099445825&amp;layer=mapnik&amp;marker=40.73414093868234%2C-73.99632096290588"
          />

          <div onClick={() => setModal(false)} className="close">
            X
          </div>
        </div>
      </div>
    )
  );
};


```
[![Edit use-click-away](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/use-click-away-ipxgh?fontsize=14&hidenavigation=1&theme=dark)

## Built With

- [React](https://reactjs.org/) - A JavaScript library for building user interfaces

## License

MIT Licensed. Copyright (c) George Bardi 2020.
