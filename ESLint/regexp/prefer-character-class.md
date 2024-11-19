Pattern: Missing use of of character class

Issue: -

## Description

Instead of single-character alternatives (e.g. `(?:a|b|c)`), character classes (e.g. `[abc]`) should be preferred.

The main reason for doing this is performance. Character classes don't require backtracking and are heavily optimized by the regex engine. On the other hand, alternatives are usually quite tricky to optimize.

## Examples

```js
/* eslint regexp/prefer-character-class: "error" */
/* ✓ GOOD */
var foo = /[abc]/
var foo = /(?:a|b)/

/* ✗ BAD */
var foo = /a|b|c/
var foo = /(a|b|c)c/
var foo = /.|abc/
var foo = /(\w|\d)+:/
```
