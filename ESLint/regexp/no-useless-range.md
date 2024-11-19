Pattern: Unnecessary character range

Issue: -

## Description

This rule reports unnecessary character ranges. E.g. `[a-a]`.

## Examples

```js
/* eslint regexp/no-useless-range: "error" */
/* ✓ GOOD */
var foo = /[a]/
var foo = /[ab]/

/* ✗ BAD */
var foo = /[a-a]/
var foo = /[a-b]/
```
