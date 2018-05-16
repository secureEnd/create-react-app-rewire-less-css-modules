# react-app-rewire-css-modules

Add LESS support in CRA.
Add [CSS Module](https://github.com/css-modules/css-modules) loaders to your [create-react-app](https://github.com/facebookincubator/create-react-app) via [react-app-rewired](https://github.com/timarney/react-app-rewired).

CSS Module styles can be written in CSS or LESS.

## Installation

This package is not yet published to the npm registry. Install from GitHub:

```
yarn add --dev secureend/create-react-app-rewire-less-css-modules
```

OR

```
npm install --save-dev secureend/create-react-app-rewire-less-css-modules
```

## Usage

Use the following file extensions for any CSS Modules styles:

* `*.module.css`
* `*.module.less`
* `*.module.scss`

Files with the following file extensions will load normally, without the CSS Modules loader:

* `*.css`
* `*.less`

### Example

In your react-app-rewired configuration:

```javascript
/* config-overrides.js */

const rewireLess = require("react-app-rewire-less-modules");
module.exports = function override(config, env) {
  // ...
  config = rewireLess(config, env);
  // ...
  return config;
};
```

In your React application:

```less
// src/App.module.less

.app {
  color: aqua;

  &:hover {
    color: lawngreen;
  }
}
```

```jsx
// src/App.js

import React from "react";
import styles from "./App.module.less";

export default ({ text }) => <div className={styles.app}>{text}</div>;
```
