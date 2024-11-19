Pattern: Missing `v` flag on regular expression

Issue: -

## Description

This rule reports regular expressions without the `v` flag.

It will automatically replace the `v` flag to regular expressions where it is already uses the 'u' flag and statically guaranteed to be safe to do so. In all other cases, the developer has to check that adding the `v` flag doesn't cause the regex to behave incorrectly.

## Examples

```js
/* eslint regexp/require-unicode-sets-regexp: "error" */
/* ✓ GOOD */
var foo = /foo/v;
var foo = /a\s+b/v;

/* ✗ BAD */
var foo = /foo/;
var foo = RegExp("a\\s+b");
var foo = /[a-z]/i;
var foo = /\S/;
var foo = /foo/u;
```
