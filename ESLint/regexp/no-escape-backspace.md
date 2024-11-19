Pattern: Use of escape backspace `[\b]`

Issue: -

## Description

This rule reports `[\b]`.
The word boundaries (`\b`) and the escape backspace (`[\b]`) are indistinguishable at a glance. This rule does not allow backspace (`[\b]`). Use Unicode escapes (`\u0008`) instead.

## Examples

```js
/* eslint regexp/no-escape-backspace: "error" */
/* ✓ GOOD */
var foo = /\b/;
var foo = /\u0008/;
var foo = /\cH/;
var foo = /\x08/;

/* ✗ BAD */
var foo = /[\b]/;
```
