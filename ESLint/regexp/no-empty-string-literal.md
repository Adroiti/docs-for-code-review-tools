Pattern: Empty string literal in character class

Issue: -

## Description

This rule reports empty string literals in character classes.

If the empty string literal is supposed to match the empty string, then use a quantifier instead. For example, `[ab\q{}]` should be written as `[ab]?`.

This rule does not report empty alternatives in string literals. (e.g. `/[\q{a|}]/v`)

## Examples

```js
/* eslint regexp/no-empty-string-literal: "error" */
/* ✓ GOOD */
var foo = /[\q{a}]/v;
var foo = /[\q{abc}]/v;
var foo = /[\q{a|}]/v;

/* ✗ BAD */
var foo = /[\q{}]/v;
var foo = /[\q{|}]/v;
```
