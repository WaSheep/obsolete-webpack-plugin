# Obsolete Webpack Plugin &middot; [![npm](https://img.shields.io/npm/v/obsolete-webpack-plugin.svg)](https://npmjs.com/package/obsolete-webpack-plugin) [![node](https://img.shields.io/node/v/obsolete-webpack-plugin.svg)](https://nodejs.org) [![licenses](https://img.shields.io/npm/l/obsolete-webpack-plugin.svg)](https://github.elenet.me/fe/obsolete-webpack-plugin/blob/master/LICENSE)

A webpack plugin generates a browser-side separate file that detects browser compatibility based on [Browserslist](https://github.com/browserslist/browserslist) and prompts website users to upgrade it.

## Getting Started

### Prerequisite

- node >=7.6.0
- webpack 4.x

### Installation

```sh
$ npm i -D obsolete-webpack-plugin
```

### Basic Usage

```js
const ObsoleteWebpackPlugin = require('obsolete-webpack-plugin');
```

```js
{
  plugins: [
    new ObsoleteWebpackPlugin()
  ]
}
```

### Best Practice

```js
const HtmlWebpackPlugin = require('html-webpack-plugin');
const ObsoleteWebpackPlugin = require('obsolete-webpack-plugin');
const ScriptExtHtmlWebpackPlugin = require('script-ext-html-webpack-plugin');
```

```js
{
  plugins: [
    new HtmlWebpackPlugin(),
    new ObsoleteWebpackPlugin(),
    new ScriptExtHtmlWebpackPlugin({
      async: 'obsolete'
    })
  ]
}
```

## Configuration

### Options

**name**

type: `{string}` default: `'obsolete'`

The chunk name.

**template**

type: `{string}` default:

```js
`<div style="position: fixed; left: 0; top: 0; background: #fff">
  Your current browser is not supported, please upgrade it to the latest version.
  <button id="obsoleteClose">&times;</button>
</div>`
```

The prompt html template injected to the bottom of body.

**browsers**

type: `{string[]}`

The browsers to support, overriding browserslist.

**promptOnNonTargetBrowser**

type: `{boolean}` default: `false`

If the current browser name doesn't match one of the target browsers, it's considered as unsupported. Thus, the prompt will be shown.

## Browser Support

TODO
