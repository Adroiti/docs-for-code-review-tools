Pattern: Unnecessary non-greedy quantifier

Issue: -

## Description

This rule reports lazy quantifiers that don't need to by lazy.

There are two reasons why a lazy quantifier doesn't have to lazy:
1. It's a constant quantifier (e.g. `a{3}?`).
2. The quantifier is effectively possessive (e.g. `a+?b`).

## Examples

```js
/* eslint regexp/no-useless-lazy: "error" */
/* ✓ GOOD */
var foo = /a*?/;
var foo = /a+?/;
var foo = /a{4,}?/;
var foo = /a[\s\S]*?bar/;

/* ✗ BAD */
var foo = /a{1}?/;
var foo = /a{4}?/;
var foo = /ab+?c/;
```
