Pattern: Unnecessary quantifier

Issue: -

## Description

This rule reports quantifiers that can trivially be removed without affecting the pattern.

This rule only fixes constant-one quantifiers (e.g. `a{1}`). All other reported useless quantifiers hint at programmer oversight or fundamental problems with the pattern.

## Examples

```js
/* eslint regexp/no-useless-quantifier: "error" */
/* ✓ GOOD */
var foo = /a*/;
var foo = /(?:a|b?)??/;
var foo = /(?:\b|(?!a))*/;

/* ✗ BAD */
var foo = /a{1}/;
var foo = /(?:\b)+/;
var foo = /(?:a+b*|c*)?/;
```
