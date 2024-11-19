Pattern: Regular expression flag that has no effect

Issue: -

## Description

This will point out present regex flags that do not change the pattern.

## Examples

```js
/* eslint regexp/no-useless-flag: "error" */
/* ✓ GOOD */
var foo = /a|b/i;

/* ✗ BAD */
var foo = /\.{3}/i;
var foo = /\w+/i;
var foo = /foo|[^\r\n]*/m;
```
