# svg-icon-to-react-component-loader

[Webpack](https://webpack.js.org/) loader that allows to load SVG files as [React](http://facebook.github.io/react/)
Stateless Functional Component.

## Installation

Using [npm](https://www.npmjs.com/):

```shell
$ npm install --save-dev svg-icon-to-react-component-loader
```

## Usage

Webpack documentation: [Using loaders](https://webpack.js.org/concepts/loaders/)

In your `webpack.config.js`, add the `svg-icon-to-react-component-loader`, chained with the [`babel-loader`](https://babeljs.io/docs/setup/#webpack2):

```js
rules: [
  {
    test: /\.svg$/,
    loaders: [
      'babel-loader', // v5
      'svg-icon-to-react-component-loader'
    ]
  }
]
```

Or you can find a working example in [test/webpack.config.js](https://github.com/frenzzy/svg-icon-to-react-component-loader/blob/master/test/webpack.config.js) file:

```js
rules: [
  {
    test: /\.(js|svg)$/i,
    loader: 'babel-loader', // v6 or later
    exclude: /node_modules/,
    query: {
      presets: ['react']
    }
  },
  {
    test: /\.svg$/i,
    loader: 'svg-icon-to-react-component-loader'
  }
]
```

### Input example

```svg
<?xml version="1.0" encoding="iso-8859-1"?>
<!-- 001-forward-icon.svg -->
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" viewBox="0 0 24 24" width="24" height="24">
  <path d="M21 11l-7-7v4C7 9 4 14 3 19c2.5-3.5 6-5.1 11-5.1V18l7-7z"/>
</svg>
```

### Output example

```js
import React from 'react';

const ForwardIcon = props => (
  <svg height="24" width="24" version="1.1" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" {...props}>
    <path d="M21 11l-7-7v4C7 9 4 14 3 19c2.5-3.5 6-5.1 11-5.1V18l7-7z"/>
  </svg>
);

export default ForwardIcon;`
```

## License

This source code is licensed under the MIT license found in the [LICENSE.txt](https://github.com/lepetitforgeron/svg-icon-to-react-component-loader/blob/master/LICENSE.txt) file.
