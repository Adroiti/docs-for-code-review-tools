Pattern: Use of `[0-9]` instead of `\d`

Issue: -

## Description

This rule is aimed at using `\d` instead of `[0-9]` in regular expressions.

## Examples

```js
/* eslint regexp/prefer-d: "error" */
/* ✓ GOOD */
var foo = /\d/;
var foo = /\D/;

/* ✗ BAD */
var foo = /[0-9]/;
var foo = /[^0-9]/;
```
