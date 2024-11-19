Pattern: Missing use of range

Issue: -

## Description

This rule is aimed to use ranges instead of multiple adjacent characters in character class.

## Examples

```js
/* eslint regexp/prefer-range: "error" */
/* ✓ GOOD */
var foo = /[0-9]/
var foo = /[a-f]/

/* ✗ BAD */
var foo = /[123456]/
var foo = /[a-cd-f]/
```
