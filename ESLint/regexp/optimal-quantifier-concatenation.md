Pattern: Suboptimal concatenation of quantifiers

Issue: -

## Description

If two quantified characters, character classes, or characters are concatenated, the quantifiers can be optimized if either of the characters elements is a subset of the other.

Let's take `\d+\w+` as an example. This can be optimized to the equivalent pattern `\d\w+`. Not only is the optimized pattern simpler, it is also faster because the first pattern might take up to _O(n^2)_ steps to fail while the optimized pattern will fail after at most _O(n)_ steps.

## Examples

```js
/* eslint regexp/optimal-quantifier-concatenation: "error" */
/* ✓ GOOD */
var foo = /\w+\d{4}/;
var foo = /\w{3,5}\d*/;
var foo = /a+b+c+d+[abc]+/;
var foo = /a\w*/;

/* ✗ BAD */
var foo = /\w+\d+/;
var foo = /\w+\d?/;
var foo = /[ab]*(?:a|b)/;
var foo = /\w+(?:(a)|b)*/;
```
