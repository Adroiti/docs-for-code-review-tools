Pattern: Non-optimized quantifier in lookaround assertion

Issue: -

## Description

This rule disallows the alternatives of lookarounds that end with a non-constant quantifier.

Non-constant quantifiers are quantifiers that describe a range (e.g. `?`, `*`, `+`, `{0,1}`, `{5,9}`, `{3,}`). They have to match some number of times (the minimum) after which further matches are optional until a certain maximum (potentially infinite) is reached.

## Examples

```js
/* eslint regexp/optimal-lookaround-quantifier: "error" */
/* ✓ GOOD */
var foo = /\w+(?=\s*:)/;
var foo = /(?<=ab+)/;

/* ✗ BAD */
var foo = /(?=ab+)/; // == /(?=ab)/
var foo = /(?=ab*)/; // == /(?=a)/
var foo = /(?!ab?)/; // == /(?!a)/
var foo = /(?!ab{6,})/; // == /(?!ab{6})/
```
