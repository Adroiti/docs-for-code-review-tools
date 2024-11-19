Pattern: Inconsistent use of hexadecimal escape

Issue: -

## Description

Characters that can use hexadecimal escape can use both hexadecimal escape and unicode escape.
This rule aims to enforce the consistent use of hexadecimal escapes.

## Examples

```js
/* eslint regexp/hexadecimal-escape: "error" */
/* ✓ GOOD */
var foo = /\x0a/;

/* ✗ BAD */
var foo = /\u000a/;
var foo = /\u{a}/u;
```
