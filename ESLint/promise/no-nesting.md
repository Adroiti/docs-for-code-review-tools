Pattern: Use of nesting promises

Issue: -

## Description

Avoid nested `then()` or `catch()` statements.

Example of **correct** code:

```js
myPromise
  .then(doSomething)
  .then(doSomethingElse)
  .catch(errors)
```

Example of **incorrect** code:

```js
myPromise.then(val => {
  doSomething(val).then(doSomethingElse)
})

myPromise.then(val => {
  doSomething(val).catch(errors)
})

myPromise.catch(err => {
  doSomething(err).then(doSomethingElse)
})

myPromise.catch(err => {
  doSomething(err).catch(errors)
})
```

## Further Reading

* [eslint-plugin-promise - no-nesting](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/no-nesting.md)