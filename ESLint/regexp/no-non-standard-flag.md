Pattern: Use of non-standard flag

Issue: -

## Description

This rule reports non-standard flags.

Some JavaScript runtime implementations allow special flags not defined in the ECMAScript standard. These flags are experimental and should not be used in production code.

## Examples

```js
/* eslint regexp/no-non-standard-flag: "error" */
/* ✓ GOOD */
var foo = /a*b*c/guy;

/* ✗ BAD */
var foo = RegExp("(?:a|a)*b", "l");
```
