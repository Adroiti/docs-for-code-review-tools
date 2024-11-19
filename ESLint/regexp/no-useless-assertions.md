Pattern: Assertion that always accepts or rejects

Issue: -

## Description

Some assertions are unnecessary because the rest of the pattern forces them to always be accept (or reject).

## Examples

```js
/* eslint regexp/no-useless-assertions: "error" */
/* ✓ GOOD */
var foo = /\bfoo\b/;

/* ✗ BAD */
var foo = /#\bfoo/;    // \b will always accept
var foo = /foo\bbar/;  // \b will always reject
var foo = /$foo/;      // $ will always reject
var foo = /(?=\w)\d+/; // (?=\w) will always accept
```
