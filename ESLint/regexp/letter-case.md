Pattern: Inconsistent letter case

Issue: -

## Description

This rule is aimed to unify the case of letters.

## Examples

```js
/* eslint regexp/letter-case: ["error", { hexadecimalEscape: 'lowercase', controlEscape: 'uppercase' }] */

/* ✓ GOOD */
var foo = /a/i
var foo = /\u000a/
var foo = /\x0a/
var foo = /\cA/

/* ✗ BAD */
var foo = /A/i
var foo = /\u000A/
var foo = /\x0A/
var foo = /\ca/

```
