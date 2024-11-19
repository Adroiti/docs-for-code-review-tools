Pattern: Missing global flag in `String#matchAll`/`String#replaceAll`

Issue: -

## Description

When calling `String#matchAll()` and `String#replaceAll()` with a `RegExp` missing the global (`g`) flag, it will be a runtime error. This rule reports `RegExp`s missing the global (`g`) flag that cause these errors.

## Examples

```js
/* eslint regexp/no-missing-g-flag: "error" */
/* ✓ GOOD */
var m = games.matchAll(/foo/g);
var newText = text.replaceAll(/Dog/ig, 'cat');

/* ✗ BAD */
var m = games.matchAll(/foo/);
var newText = text.replaceAll(/Dog/i, 'cat');
```
