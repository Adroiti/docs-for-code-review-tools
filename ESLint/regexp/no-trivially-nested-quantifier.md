Pattern: Nested quantifier that can be rewritten as one

Issue: -

## Description

In some cases, nested quantifiers can be rewritten as one quantifier (e.g. `(?:a{1,2}){3}` -> `a{3,6}`).

## Examples

```js
/* eslint regexp/no-trivially-nested-quantifier: "error" */
/* ✓ GOOD */
var foo = /(a{1,2})+/;  // the rule won't touch capturing groups
var foo = /(?:a{2})+/;

/* ✗ BAD */
var foo = /(?:a{1,2})+/;
var foo = /(?:a{1,2}){3,4}/;
var foo = /(?:a{4,}){5}/;
```
