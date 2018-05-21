Pattern: Calling `new` on a Promise static method

Issue: -

## Description

Calling a Promise static method with `new` is invalid, resulting in a `TypeError` at runtime.

Examples for **incorrect** code for this rule:

```js
new Promise.resolve(value)
new Promise.reject(error)
new Promise.race([p1, p2])
new Promise.all([p1, p2])
```

Examples for **correct** code for this rule:

```js
Promise.resolve(value)
Promise.reject(error)
Promise.race([p1, p2])
Promise.all([p1, p2])
```

## When Not To Use It

If you do not want to be notified when calling `new` on a Promise static method,
you can safely disable this rule.


## Further Reading

* [eslint-plugin-promise - no-new-statics](https://github.com/xjamundx/eslint-plugin-promise/blob/master/docs/rules/no-new-statics.md)