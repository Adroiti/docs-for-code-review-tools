Pattern: Unnecessarily complex set operation

Issue: -

## Description

This rule aims to optimize patterns by simplifying set operations in character classes (with `v` flag).

This rule uses De Morgan's laws and conversion between intersection and subtraction to simplify character class operations.

## Examples

```js
/* eslint regexp/simplify-set-operations: "error" */
/* ✓ GOOD */
var re = /[a--b]/v;
var re = /[a&&b]/v;
var re = /[^ab]/v;
var re = /[^a&&b]/v;

/* ✗ BAD */
var re = /[a&&[^b]]/v; // -> /[a--b]/v
var re = /[[^b]&&a]/v; // -> /[a--b]/v
var re = /[a--[^b]]/v; // -> /[a&&b]/v
var re = /[[^a]&&[^b]]/v; // -> /[^ab]/v
```
