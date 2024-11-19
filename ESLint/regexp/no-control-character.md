Pattern: Use of control character

Issue: -

## Description

This rule reports control characters.

This rule is inspired by the `no-control-regex` rule. The positions of reports are improved over the core rule and suggestions are provided in some cases.

## Examples

```js
/* eslint regexp/no-control-character: "error" */
/* ✓ GOOD */
var foo = /\n/;
var foo = RegExp("\n");

/* ✗ BAD */
var foo = /\x1f/;
var foo = /\x0a/;
var foo = RegExp('\x0a');
```
