Pattern: Single character alternative in `\q{...}`

Issue: -

## Description

This rule reports the string alternatives of a single character in `\q{...}`.
It can be placed outside `\q{...}`.

## Examples

```js
/* eslint regexp/no-useless-string-literal: "error" */
/* ✓ GOOD */
var foo = /[\q{abc}]/v
var foo = /[\q{ab|}]/v

/* ✗ BAD */
var foo = /[\q{a}]/v // => /[a]/v
var foo = /[\q{a|bc}]/v // => /[a\q{bc}]/v
```
