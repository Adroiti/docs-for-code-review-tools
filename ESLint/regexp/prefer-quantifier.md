Pattern: Missing use of quantifier

Issue: -

## Description

This rule is aimed to use quantifiers instead of consecutive characters in regular expressions.

## Examples

```js
/* eslint regexp/prefer-quantifier: "error" */
/* ✓ GOOD */
var foo = /\d{4}-\d{2}-\d{2}/;

/* ✗ BAD */
var foo = /\d\d\d\d-\d\d-\d\d/;
```
