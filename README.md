# Anti Redux

## Documents

* [React v16.3: New lifecycles and Context API](https://reactjs.org/blog/2018/03/29/react-v-16-3.html)

## Setup

```bash
]$ yarn add typography styled-components styled-reset styled-flex-component react-fontawesome
```

## Usage

```javascript
/// store.js
import React from "react";

// Create context with default value
const Store = React.createContext(null);

export default Store;

/// Provider.js
import Store from "store";
class AppContainer extends Component {
  constructor(props) {
    super(props);

    this._seeNotification = id => {
      /// ...
    };

    this.state = {
      notifications: {},
      seeNotification: this._seeNotification,
    };
  }

  render() {
    return (
      <Store.Provider value={this.state}>
        <AppPresenter />
      </Store.Provider>
    );
  }
}

/// Consumer
import Store from "store";
<Store.Consumer>
  {store => (
    <Fragment>
      <Button success seen={seen} onClick={() => store.seeNotification(id)}>
        <FontAwesome name="check" />
      </Button>
      <Button danger seen={seen} onClick={() => {}}>
        <FontAwesome name="times" />
      </Button>
    </Fragment>
  )}
</Store.Consumer>;
```

## React Suspense
