Pattern: Missing use of object spread property

Issue: -

## Description

This rule suggests that [object spread properties](https://github.com/sebmarkbage/ecmascript-rest-spread) be used instead of `Object.assign()`. The rule is only applied when Object.assign() is used for cloning; not when it is used to extend an existing object. i.e., it applies when the first argument to `Object.assign()` is an object literal. This is because spread properties only iterate over own properties.

## Examples

When using this rule the following patterns are considered problems:

```js
var a = Object.assign({}, foo); // error Use a spread property instead of Object.assign().

var b = Object.assign({ c: 1 }, bar); // error Use a spread property instead of Object.assign().
```

The following patterns are considered okay:
```js
var a = { ...foo };

var b = { c: 1, ...bar };

Object.assign(b, { d: 2 });
```
