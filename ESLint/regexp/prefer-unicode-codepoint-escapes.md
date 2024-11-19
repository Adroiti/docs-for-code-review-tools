Pattern: Missing use of use of Unicode codepoint escapes

Issue: -

## Description

This rule enforces the use of Unicode codepoint escapes instead of Unicode escapes using surrogate pairs.

If you want to enforce characters that do not use surrogate pairs into Unicode escapes or Unicode code point escapes, use the `regexp/unicode-escape` rule.

## Examples

```js
/* eslint regexp/prefer-unicode-codepoint-escapes: "error" */
/* ✓ GOOD */
var foo = /\u{1f600}/u
var foo = /😀/u

/* ✗ BAD */
var foo = /\ud83d\ude00/u
```
