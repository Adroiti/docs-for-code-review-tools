Pattern: Duplicate character in character class

Issue: -

## Description

Because multiple same character classes in regular expressions only one is useful, they might be typing mistakes.

## Examples

```js
/* eslint regexp/no-dupe-characters-character-class: "error" */
/* ✓ GOOD */
var foo = /[\(\)]/;
var foo = /[a-z\s]/;
var foo = /[\w]/;

/* ✗ BAD */
var foo = /[\\(\\)]/;
var foo = /[a-z\\s]/;
var foo = /[\w0-9]/;
```
