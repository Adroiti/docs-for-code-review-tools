Pattern: Standalone backslash without escape

Issue: -

## Description

This rule disallows backslash (`\`) without escape.

E.g. the regular expression `/\c/` without the Unicode (`u`) flag is the same pattern as `/\\c/`.

In most cases, standalone backslashes are used by accident when a control escape sequence (`\cX`) or another escape sequence was intended. They are very confusing and should not be used intentionally.

## Examples

```js
/* eslint regexp/no-standalone-backslash: "error" */
/* ✓ GOOD */
var foo = /\cX/;

/* ✗ BAD */
var foo = /\c/;
var foo = /\c-/;
var foo = /[\c]/;
```
