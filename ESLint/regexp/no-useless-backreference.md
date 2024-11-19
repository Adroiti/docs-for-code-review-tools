Pattern: Unnecessary backreference

Issue: -

## Description

Backreferences that will always trivially accept serve no function and can be removed.

This rule identifies backreferences that are useless for multiple reasons including empty capturing groups, nested backreferences, different alternatives, and forward/backward references.

## Examples

```js
/* eslint regexp/no-useless-backreference: "error" */
/* ✓ GOOD */
var foo = /(a)b\1/;
var foo = /(a?)b\1/;
var foo = /(\b|a)+b\1/;

/* ✗ BAD */
var foo = /\1(a)/;
var foo = /(a\1)/;
var foo = /(a)|\1/;
var foo = /(\b)a\1/;
```
