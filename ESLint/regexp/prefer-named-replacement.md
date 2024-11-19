Pattern: Missing use of named replacement

Issue: -

## Description

This rule reports and fixes `$n` parameter in replacement string that do not use the name of their referenced capturing group.

## Examples

```js
/* eslint regexp/prefer-named-replacement: "error" */
/* ✓ GOOD */
"abc".replace(/a(?<foo>b)c/, '$<foo>');
"abc".replace(/a(b)c/, '$1');

/* ✗ BAD */
"abc".replace(/a(?<foo>b)c/, '$1');
```
