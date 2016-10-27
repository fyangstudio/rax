<p align="center">
  <a href="https://alibaba.github.io/rx">
    <img alt="Rx" src="https://gw.alicdn.com/L1/461/1/40137b64ab73a123e78d8246cd81c8379358c999_400x400.jpg" width="200">
  </a>
</p>

<p align="center">
A universal React-compatible render engine.
</p>

<p align="center">
<img src="https://img.shields.io/npm/l/universal-rx.svg">
<img src="https://img.shields.io/npm/v/universal-rx.svg">
<img src="https://img.shields.io/npm/dm/universal-rx.svg">
</p>

---

Rx is a universal JavaScript library with a largely React-compatible API. If you use React, you already know how to use Rx.

**Fast:** blazing fast virtual DOM.

**Tiny:** 8kb only after min+gzip.

[Angular 1.5.8](https://unpkg.com/angular@1.5.8/angular.min.js) - 55.4kb (gzip)

<img src="http://ata2-img.cn-hangzhou.img-pub.aliyun-inc.com/616195344a3b5546f1e059d7931e2d2c" height="5" width="100%">

[React 15.3.2](https://unpkg.com/react@15.3.2/dist/react.min.js) - 43.7kb (gzip)

<img src="http://ata2-img.cn-hangzhou.img-pub.aliyun-inc.com/616195344a3b5546f1e059d7931e2d2c" height="5" width="78.88%">

[Vue 2.0.3](https://unpkg.com/vue@2.0.3/dist/vue.min.js) - 23.2kb (gzip)

<img src="http://ata2-img.cn-hangzhou.img-pub.aliyun-inc.com/616195344a3b5546f1e059d7931e2d2c" height="5" width="41.87%">

[Rx 0.0.3](https://unpkg.com/universal-rx@0.0.3/dist/rx.min.js) - 8kb (gzip)

<img src="http://ata2-img.cn-hangzhou.img-pub.aliyun-inc.com/616195344a3b5546f1e059d7931e2d2c" height="5" width="14.44%">

**Universal:** cross browser、Weex and Node.js.

## Installation

### Compatibility Note

Rx does not support IE8 and below, because it uses ECMAScript 5 features that are un-shimmable in IE8. However it supports all ECMAScript 5 compliant browsers.

### NPM
We recommend using Rx from npm with `webpack`. If you use npm for client package management, you can install Rx with:
```sh
npm install --save universal-rx
```

### CDN

If you don't want to use `npm` to manage client packages, the `rx` npm packages also provide UMD distributions in `dist` folders, which are hosted on a CDN:
```html
<script src="https://unpkg.com/universal-rx@1/dist/rx.js"></script>
```

To load a specific version of `rx`, replace `1` with the version number.
Minified production versions of `rx` are available at:
```html
<script src="https://unpkg.com/universal-rx@1/dist/rx.min.js"></script>
```

## Example

```js
import {createElement, Component, render} from 'universal-rx';

class Hello extends Component {
  render() {
    return <text style={styles.title}>Hello {this.props.name}</text>;
  }
}

const styles = {
  title: {
    color: '#ff4400',
    fontSize: 48,
    fontWeight: 'bold',
  }
};

render(<Hello name="world" />);
```

## Top-level API

* createElement
* cloneElement
* createFactory
* render
* Component
* PureComponent
* PropTypes
* findDOMNode
* unmountComponentAtNode
* findComponentInstance
* setNativeProps

## Difference with React

* No `createClass()` method，use ES6 class by `extends Component` class instead of calling createClass

```js
// Before
import React from 'react';

const Hi = React.createClass({
  render() {
    return (
      <text>hi</text>
    );
  }
});

export default Hi;
```

```js
// After
import {createElement, Component} from 'universal-rx';

class Hi extends Component {
  render() {
    return (
      <text>hi</text>
    );
  }
}

export default Hi;
```

* Render to new container node not clear existed children
* The `findDOMNode()` method accept id which is string type

```js
import {createElement, render, findDOMNode} from 'universal-rx';

class Hi extends Component {
  render() {
    return (
      <text id="hi">hi</text>
    );
  }
}

render(<Hi />, document.body);
const node = findDOMNode('hi');
```

* `PropTypes` not check in production

## Packages

| Package | Version | External Deps | Vulnerabilities |
|--------|-------|------------|-----------|
| [`universal-rx`](/packages/universal-rx) | [![npm](https://img.shields.io/npm/v/universal-rx.svg)](https://www.npmjs.com/package/universal-rx) | [![Dependency Status](https://david-dm.org/alibaba/rx.svg?path=packages/universal-rx)](https://david-dm.org/alibaba/rx.svg?path=packages/universal-rx) | [![Known Vulnerabilities](https://snyk.io/test/npm/universal-rx/badge.svg)](https://snyk.io/test/npm/universal-rx) |
| [`universal-env`](/packages/universal-env) | [![npm](https://img.shields.io/npm/v/universal-env.svg)](https://www.npmjs.com/package/universal-env) | [![Dependency Status](https://david-dm.org/alibaba/rx.svg?path=packages/universal-env)](https://david-dm.org/alibaba/rx.svg?path=packages/universal-env) | [![Known Vulnerabilities](https://snyk.io/test/npm/universal-env/badge.svg)](https://snyk.io/test/npm/universal-env) |
| [`rx-webpack-plugin`](/packages/rx-webpack-plugin) | [![npm](https://img.shields.io/npm/v/rx-webpack-plugin.svg)](https://www.npmjs.com/package/rx-webpack-plugin) | [![Dependency Status](https://david-dm.org/alibaba/rx.svg?path=packages/rx-webpack-plugin)](https://david-dm.org/alibaba/rx.svg?path=packages/rx-webpack-plugin) | [![Known Vulnerabilities](https://snyk.io/test/npm/rx-webpack-plugin/badge.svg)](https://snyk.io/test/npm/rx-webpack-plugin) |
| [`babel-preset-rx`](/packages/babel-preset-rx) | [![npm](https://img.shields.io/npm/v/babel-preset-rx.svg)](https://www.npmjs.com/package/babel-preset-rx) | [![Dependency Status](https://david-dm.org/alibaba/rx.svg?path=packages/babel-preset-rx)](https://david-dm.org/alibaba/rx.svg?path=packages/babel-preset-rx) | [![Known Vulnerabilities](https://snyk.io/test/npm/babel-preset-rx/badge.svg)](https://snyk.io/test/npm/babel-preset-rx) |
