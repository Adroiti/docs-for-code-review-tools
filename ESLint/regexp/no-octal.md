Pattern: Use of octal escape sequence

Issue: -

## Description

This rule reports octal escapes.

`\0` matches the `NUL` character. However, if `\0` is followed by another digit, it will become an octal escape sequence (e.g. `\07`).

Octal escapes can also easily be confused with backreferences. The same character sequence (e.g. `\3`) can either escape a character or be a backreference depending on the number of capturing groups in the pattern.

## Examples

```js
/* eslint regexp/no-octal: "error" */
/* ✓ GOOD */
var foo = /\0/;
var foo = /=/;
var foo = /(a)\1/;

/* ✗ BAD */
var foo = /\075/;
var foo = /\1/;
```
