Pattern: Duplicate disjunction

Issue: -

## Description

This rule disallows duplicate disjunctions. Duplicate disjunctions make the pattern less efficient and may indicate a mistake in the pattern.

## Examples

```js
/* eslint regexp/no-dupe-disjunctions: "error" */

/* ✓ GOOD */
var foo = /a|b/
var foo = /(a|b)/
var foo = /(?:a|b)/

/* ✗ BAD */
var foo = /a|a/
var foo = /(a|a)/
var foo = /(?:a|a)/
var foo = /abc|abc/
var foo = /[ab]|[ba]/
var foo = /a|abc/
var foo = /.|abc/
var foo = /.|a|b|c/
```
