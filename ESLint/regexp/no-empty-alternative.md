Pattern: Empty alternative in pattern

Issue: -

## Description

While (re-)writing long regular expressions, it can happen that one forgets to remove the `|` character of a former alternative. This rule tries to point out these potential mistakes by reporting all empty alternatives.

If the empty alternative is supposed to match the empty string, then use a quantifier instead. For example, `a|` should be written as `a?`.

## Examples

```js
/* eslint regexp/no-empty-alternative: "error" */
/* ✓ GOOD */
var foo = /(?:)/
var foo = /a+|b*/

/* ✗ BAD */
var foo = /a+|b+|/
var foo = /\|\||\|||\|\|\|/
var foo = /a(?:a|bc|def|h||ij|k)/
```
