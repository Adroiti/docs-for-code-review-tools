Pattern: Missing return for `then()`

Issue: -

## Description

Ensure that inside a `then()` you make sure to `return` a new promise or value.

This rule also allows to `throw` inside a `then()` which is essentially the same as `return Promise.reject()`.

Example of **correct** code:

```js
myPromise.then((val) => val * 2));
myPromise.then(function(val) { return val * 2; });
myPromise.then(doSomething); // could be either
myPromise.then((b) => { if (b) { return "yes" } else { return "no" } });
```

Example of **incorrect** code:

```js
myPromise.then(function(val) {})
myPromise.then(() => {
  doSomething()
})
myPromise.then(b => {
  if (b) {
    return 'yes'
  } else {
    forgotToReturn()
  }
})
```

## Further Reading

* [Nolan Lawson - We have a problem with promises](https://pouchdb.com/2015/05/18/we-have-a-problem-with-promises.html)
* [eslint-plugin-promise - always-return](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/always-return.md)