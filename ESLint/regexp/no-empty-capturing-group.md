Pattern: Empty capturing group

Issue: -

## Description

This rule reports capturing group that captures assertions.

## Examples

```js
/* eslint regexp/no-empty-capturing-group: "error" */

/* ✓ GOOD */
var foo = /(a)/;
var foo = /a(?:\b)/;
var foo = /a(?:$)/;
var foo = /(?:^)a/;
var foo = /(?:^|b)a/;

/* ✗ BAD */
var foo = /a(\b)/;
var foo = /a($)/;
var foo = /(^)a/;

```
