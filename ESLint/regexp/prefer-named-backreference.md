Pattern: Missing use of named backreference

Issue: -

## Description

This rule reports and fixes backreferences that do not use the name of their referenced capturing group.

## Examples

```js
/* eslint regexp/prefer-named-backreference: "error" */
/* ✓ GOOD */
var foo = /(a)\1/
var foo = /(?<foo>a)\k<foo>/

/* ✗ BAD */
var foo = /(?<foo>a)\1/
```
