Pattern: Missing `i` flag where it would simplify pattern

Issue: -

## Description

This rule reports regular expressions that can be simplified by adding the `i` flag.

## Examples

```js
/* eslint regexp/use-ignore-case: "error" */
/* ✓ GOOD */
var foo = /\w\d+a/;
var foo = /\b0x[a-f0-9]+\b/;

/* ✗ BAD */
var foo = /[a-zA-Z]/;
var foo = /\b0[xX][a-fA-F0-9]+\b/;
```
