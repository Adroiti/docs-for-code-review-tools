Pattern: Missing use of `\w`

Issue: -

## Description

This rule is aimed at using `\w` in regular expressions.

## Examples

```js
/* eslint regexp/prefer-w: "error" */

/* ✓ GOOD */
var foo = /\w/;
var foo = /\W/;

/* ✗ BAD */
var foo = /[0-9a-zA-Z_]/;
var foo = /[^0-9a-zA-Z_]/;
var foo = /[0-9a-z_]/i;
var foo = /[0-9a-z_-]/i;
```
