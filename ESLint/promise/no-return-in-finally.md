Pattern: Use of `return` in `finally()`

Issue: -

## Description

Disallow return statements inside a callback passed to `finally()`, since nothing would consume what's returned.

Example of **correct** code:

```js
myPromise.finally(function(val) {
  console.log('value:', val)
})
```

Example of **incorrect** code:

```js
myPromise.finally(function(val) {
  return val
})
```

## Further Reading

* [eslint-plugin-promise - no-return-in-finally](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/no-return-in-finally.md)