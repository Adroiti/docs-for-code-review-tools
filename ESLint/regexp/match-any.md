Pattern: Inconsistent pattern for matching any character

Issue: -

## Description

This rule enforces the regular expression notation to match any character.
e.g. `[\s\S]`, `[^]`, `/./s` (dotAll) and more.

## Examples

```js
/* eslint regexp/match-any: "error" */
/* ✓ GOOD */
var foo = /[\s\S]/;
var foo = /./s;

/* ✗ BAD */
var foo = /[\S\s]/;
var foo = /[^]/;
var foo = /[\d\D]/;
var foo = /[\w\W]/;
```
