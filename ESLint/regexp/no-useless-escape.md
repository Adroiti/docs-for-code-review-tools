Pattern: Unnecessary escape character

Issue: -

## Description

This rule reports unnecessary escape characters in RegExp.
You may be able to find another mistake by finding unnecessary escapes.

## Examples

```js
/* eslint regexp/no-useless-escape: "error" */
/* ✓ GOOD */
var foo = /\[/
var foo = /\\/

/* ✗ BAD */
var foo = /\a/
var foo = /\x7/
var foo = /\u41/
var foo = /\u{[41]}/
```
