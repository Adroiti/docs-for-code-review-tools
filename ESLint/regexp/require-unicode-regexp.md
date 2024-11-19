Pattern: Missing `u` flag on regular expression

Issue: -

## Description

This rule reports regular expressions without the `u` flag.

It will automatically add the `u` flag to regular expressions where it is statically guaranteed to be safe to do so. In all other cases, the developer has to check that adding the `u` flag doesn't cause the regex to behave incorrectly.

## Examples

```js
/* eslint regexp/require-unicode-regexp: "error" */
/* ✓ GOOD */
var foo = /foo/u;
var foo = /a\s+b/u;

/* ✗ BAD */
var foo = /foo/;
var foo = RegExp("a\\s+b");
var foo = /[a-z]/i;
var foo = /\S/;
```
