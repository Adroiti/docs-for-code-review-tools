Pattern: Use of `{1,}` instead of `+` quantifier

Issue: -

## Description

This rule is aimed at using `+` quantifier instead of `{1,}` in regular expressions.

## Examples

```js
/* eslint regexp/prefer-plus-quantifier: "error" */
/* ✓ GOOD */
var foo = /a+/;

/* ✗ BAD */
var foo = /a{1,}/;
```
