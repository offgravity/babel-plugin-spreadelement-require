[![NPM version](https://img.shields.io/npm/v/babel-plugin-spreadelement-require.svg?style=flat)](https://npmjs.org/package/babel-plugin-spreadelement-require) [![Build Status](https://travis-ci.org/offgravity/babel-plugin-spreadelement-require.svg?branch=master)](https://travis-ci.org/offgravity/babel-plugin-spreadelement-require)
 [![Coverage Status](https://coveralls.io/repos/github/offgravity/babel-plugin-spreadelement-require/badge.svg?branch=master)](https://coveralls.io/github/offgravity/babel-plugin-spreadelement-require?branch=master)
# babel-plugin-spreadelement-require

A babel plugin to transform from { ...require('xxx')} to const xxx = require('xxx');{ ...xxx }.

## Example

```javascript
const x = {
  ...require('./a.js'),
  y: 1,
}

      ↓ ↓ ↓ ↓ ↓ ↓
      
const spreadelement_require_{randomnumber} = require('./a.js');
const x = {
  ...spreadelement_require_{randomnumber},
  y: 1,
}
```

## Install

```sh
npm install --save babel-plugin-spreadelement-require
```

## Usage

Via `.babelrc` or babel-loader.

```js
{
  "plugins": [["spreadelement-require"]]
}
```


## Options

| Option             | Defaults | Description                                                                                                                                                                                                                              |
| ------------------ | :------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| warn |  false   | Throw an error insteads of transfoming it. |                                                                                                                     |

## More examples

`["spreadelement-require", { warn: true }]`

