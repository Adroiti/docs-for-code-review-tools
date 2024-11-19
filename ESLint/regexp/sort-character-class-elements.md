Pattern: Unsorted elements in character class

Issue: -

## Description

This rule checks elements of character classes are sorted.

## Examples

```js
/* eslint regexp/sort-character-class-elements: "error" */
/* ✓ GOOD */
var foo = /[abcdef]/
var foo = /[ab-f]/

/* ✗ BAD */
var foo = /[bcdefa]/
var foo = /[b-fa]/
```
