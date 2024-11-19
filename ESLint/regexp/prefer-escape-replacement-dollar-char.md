Pattern: Unescaped dollar sign in replacement pattern

Issue: -

## Description

This rule aims to enforce correct dollar sign escapes (`$$`) when using `$` in replacement pattern of string replacements.

## Examples

```js
/* eslint regexp/prefer-escape-replacement-dollar-char: "error" */
/* ✓ GOOD */
'€1,234'.replace(/€/, '$$'); // "$1,234"

/* ✗ BAD */
'€1,234'.replace(/€/, '$'); // "$1,234"
```
