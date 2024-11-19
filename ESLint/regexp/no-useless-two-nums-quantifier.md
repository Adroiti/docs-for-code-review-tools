Pattern: Unnecessary `{n,m}` quantifier when `n` equals `m`

Issue: -

## Description

This rule is aimed at using simpler quantifiers instead of `{n,m}` when n equals m in regular expressions.

## Examples

```js
/* eslint regexp/no-useless-two-nums-quantifier: "error" */
/* ✓ GOOD */
var foo = /a{0,1}/;
var foo = /a{1,5}/;
var foo = /a{1,}/;
var foo = /a{2}/;

/* ✗ BAD */
var foo = /a{0,0}/;
var foo = /a{1,1}/;
var foo = /a{2,2}/;
```
