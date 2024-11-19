Pattern: Unsorted alternatives

Issue: -

## Description

This rule will sort alternatives to improve readability and maintainability.

The primary target of this rule are lists of words and/or numbers. These lists are somewhat common, and sorting them makes it easy for readers to check whether a particular word or number is included.

## Examples

```js
/* eslint regexp/sort-alternatives: "error" */

/* ✓ GOOD */
var foo = /\b(1|2|3)\b/;
var foo = /\b(alpha|beta|gamma)\b/;
var foo = /[\q{blue|green|red}]/v;

/* ✗ BAD */
var foo = /\b(2|1|3)\b/;
var foo = /__(?:Foo|Bar)__/;
var foo = /\((?:TM|R|C)\)/;
var foo = /[\q{red|green|blue}]/v;

```
