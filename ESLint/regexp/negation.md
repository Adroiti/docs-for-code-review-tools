Pattern: Missing use of escape on negation

Issue: -

## Description

This rule enforces use of `\D`, `\W`, `\S` and `\P` on negation.

## Examples

```js
/* eslint regexp/negation: "error" */

/* ✓ GOOD */
var foo = /\D/
var foo = /\W/
var foo = /\S/
var foo = /\P{ASCII}/u

var foo = /\d/
var foo = /\w/
var foo = /\s/
var foo = /\p{ASCII}/u

/* ✗ BAD */
var foo = /[^\d]/
var foo = /[^\w]/
var foo = /[^\s]/
var foo = /[^\p{ASCII}]/u

var foo = /[^\D]/
var foo = /[^\W]/
var foo = /[^\S]/
var foo = /[^\P{ASCII}]/u
```
