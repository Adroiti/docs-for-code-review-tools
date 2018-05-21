Pattern: Wrapping in `Promise.resolve` or `Promise.reject`

Issue: -

## Description

Ensure that inside a `then()` or a `catch()` we always `return` or `throw` a raw value instead of wrapping in `Promise.resolve` or `Promise.reject`

Example of **correct** code:

```js
myPromise.then(function(val) {
  return val * 2
})
myPromise.then(function(val) {
  throw 'bad thing'
})
```

Example of **incorrect** code:

```js
myPromise.then(function(val) {
  return Promise.resolve(val * 2)
})
myPromise.then(function(val) {
  return Promise.reject('bad thing')
})
```

## Options

### `allowReject`

Pass `{ allowReject: true }` as an option to this rule to permit wrapping
returned values with `Promise.reject`, such as when you would use it as another
way to reject the promise.

### `param-names`

Enforce standard parameter names for Promise constructors

Example of **correct** code:

```js
new Promise(function (resolve) { ... })
new Promise(function (resolve, reject) { ... })
```

Example of **incorrect** code:

```js
new Promise(function (reject, resolve) { ... }) // incorrect order
new Promise(function (ok, fail) { ... }) // non-standard parameter names
```

Ensures that `new Promise()` is instantiated with the parameter names `resolve, reject` to avoid confusion with order such as `reject, resolve`. 
The Promise constructor uses the [RevealingConstructor pattern](https://blog.domenic.me/the-revealing-constructor-pattern).
Using the same parameter names as the language specification makes code more uniform and easier to understand.

## Further Reading

* [eslint-plugin-promise - no-return-wrap](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/no-return-wrap.md)