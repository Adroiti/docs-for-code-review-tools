Pattern: Quantifier with maximum of zero

Issue: -

## Description

This rule reports quantifiers with a maximum of zero. These quantifiers trivially do not affect the pattern is any way and can be removed.

## Examples

```js
/* eslint regexp/no-zero-quantifier: "error" */
/* ✓ GOOD */
var foo = /a?/;
var foo = /a{0,}/;
var foo = /a{0,1}/;

/* ✗ BAD */
var foo = /a{0}/;
var foo = /a{0,0}?/;
var foo = /(a){0}/;
```
