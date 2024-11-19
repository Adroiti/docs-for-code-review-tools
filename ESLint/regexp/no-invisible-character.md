Pattern: Use of invisible raw character

Issue: -

## Description

This rule disallows using invisible characters other than SPACE (`U+0020`) without using escapes.

## Examples

```js
/* eslint regexp/no-invisible-character: "error" */
/* ✓ GOOD */
var foo = /\t/;
var foo = /\v/;
var foo = /\f/;
var foo = /\u3000/;
var foo = / /; // SPACE (`U+0020`)

/* ✗ BAD */
var foo = /	/;
var foo = //;
var foo = //;
var foo = /　/;
```
