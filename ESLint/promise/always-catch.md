Pattern: Unreturned promise

Issue: -

## Description

Ensure that each time a `then()` is applied to a promise, a `catch()` is applied
as well. Exceptions are made if you are returning that promise.

Example of **correct** code:

```js
myPromise.then(doSomething).catch(errors)
myPromise
  .then(doSomething)
  .then(doSomethingElse)
  .catch(errors)
function doSomethingElse() {
  return myPromise.then(doSomething)
}
```

Example of **incorrect** code:

```js
myPromise.then(doSomething)
myPromise.then(doSomething, catchErrors) // catch() may be a little better
function doSomethingElse() {
  myPromise.then(doSomething)
}
```

## Options

### `allowThen`

You can pass an `{ allowThen: true }` as an option to this rule to allow for
`.then(null, fn)` to be used instead of `catch()` at the end of the promise
chain.

### `terminationMethod`

You can pass a `{ terminationMethod: 'done' }` as an option to this rule to
require `done()` instead of `catch()` at the end of the promise chain. This is
useful for many non-standard Promise implementations.

You can also pass an array of methods such as
`{ terminationMethod: ['catch', 'asCallback', 'finally'] }`.

This will allow any of

```js
Promise.resolve(1)
  .then(() => {
    throw new Error('oops')
  })
  .catch(logerror)
Promise.resolve(1)
  .then(() => {
    throw new Error('oops')
  })
  .asCallback(cb)
Promise.resolve(1)
  .then(() => {
    throw new Error('oops')
  })
  .finally(cleanUp)
```


## Further Reading

* [eslint-plugin-promise - catch-or-return](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/catch-or-return.md)