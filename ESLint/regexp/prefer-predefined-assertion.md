Pattern: Lookaround used where predefined assertion exists

Issue: -

## Description

All predefined assertions (`\b`, `\B`, `^`, and `$`) can be expressed as lookaheads and lookbehinds. E.g. `/a$/` is the same as `/a(?![^])/`.

In most cases, it's better to use the predefined assertions because they are better known.

## Examples

```js
/* eslint regexp/prefer-predefined-assertion: "error" */

/* ✓ GOOD */
var foo = /a(?=\W)/;

/* ✗ BAD */
var foo = /a(?![^])/;
var foo = /a(?!\w)/;
var foo = /a+(?!\w)(?:\s|bc+)+/;

```
