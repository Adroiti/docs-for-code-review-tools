Pattern: Non-obvious character range usage

Issue: -

## Description

The character range operator (the `-` inside character classes) can easily be misused (mostly unintentionally) to construct non-obvious character class. This rule will disallow all non-obvious uses of the character range operator.

## Examples

```js
/* eslint regexp/no-obscure-range: "error" */
/* ✓ GOOD */
var foo = /[a-z]/;
var foo = /[J-O]/;
var foo = /[1-9]/;
var foo = /[\x00-\x40]/;

/* ✗ BAD */
var foo = /[A-\x43]/;
var foo = /[\41-\x45]/;
var foo = /[!-$]/;
var foo = /[😀-😄]/u;
```
