Pattern: Not strictly valid regular expression pattern

Issue: -

## Description

This rule disallows not strictly valid regular expressions.

An invalid pattern in a regular expression literal is a `SyntaxError` when the code is parsed. However, it is not always strictly checked.

Depending on the syntax defined in `Annex B` of the ECMAScript specification, some ambiguous pattern syntax may also succeed in parsing as a valid pattern. This rule reports these ambiguous patterns.

## Examples

```js
/* eslint regexp/strict: "error" */
/* ✓ GOOD */
var foo = /\}/
var foo = /\{/
var foo = /\]/
var foo = /\u{42}/u; // It matches "B"
var foo = /u{42}/; // It matches a string followed by 42 "u"s

/* ✗ BAD */
var foo = /}/
var foo = /{/
var foo = /]/
var foo = /\u{42}/; // It matches a string followed by 42 "u"s
```
