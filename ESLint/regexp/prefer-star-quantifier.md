Pattern: Use of `{0,}` instead of `*` quantifier

Issue: -

## Description

This rule is aimed at using `*` quantifier instead of `{0,}` in regular expressions.

## Examples

```js
/* eslint regexp/prefer-star-quantifier: "error" */
/* ✓ GOOD */
var foo = /a*/

/* ✗ BAD */
var foo = /a{0,}/;
```
