Pattern: Use of `{0,1}` instead of `?` quantifier

Issue: -

## Description

This rule is aimed at using `?` quantifier instead of `{0,1}` in regular expressions.

## Examples

```js
/* eslint regexp/prefer-question-quantifier: "error" */
/* ✓ GOOD */
var foo = /a?/;

/* ✗ BAD */
var foo = /a{0,1}/;
```
