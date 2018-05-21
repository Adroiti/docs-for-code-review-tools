Pattern: Missing `Promise` constructor before use

Issue: -

## Description

Ensure that `Promise` is included fresh in each file instead of relying on the
existence of a native promise implementation. Helpful if you want to use
`bluebird` or if you don't intend to use an ES6 Promise shim.

Example of **correct** code:

```js
var Promise = require('bluebird')
var x = Promise.resolve('good')
```

Example of **incorrect** code:

```js
var x = Promise.resolve('bad')
```


## Further Reading

* [eslint-plugin-promise - no-native](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/no-native.md)