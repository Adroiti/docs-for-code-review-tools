Pattern: Missing use of `RegExp#test`

Issue: -

## Description

This rule is aimed to use `RegExp#test` to check if a pattern matches a string.

## Examples

```js
/* eslint regexp/prefer-regexp-test: "error" */

const text = 'something';
const pattern = /thing/;

/* ✓ GOOD */
if (pattern.test(text)) {}

/* ✗ BAD */
if (pattern.exec(text)) {}
if (text.match(pattern)) {}

```
