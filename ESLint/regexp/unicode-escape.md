Pattern: Inconsistent Unicode escape style

Issue: -

## Description

This rule aims to enforce the consistent use of Unicode escapes or Unicode code point escapes.

This rule does not check for characters that require surrogate pairs and patterns that do not have the `u` flag.

## Examples

```js
/* eslint regexp/unicode-escape: "error" */
/* ✓ GOOD */
var foo = /\u{41}/u;
var foo = /\u0041/; // do not have the `u` flag
var foo = /\ud83d\ude00/u; // surrogate pair

/* ✗ BAD */
var foo = /\u0041/u;
```
