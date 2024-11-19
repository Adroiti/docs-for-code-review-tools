Pattern: Quantifier causing quadratic moves across input

Issue: -

## Description

This rule reports super-linear worst-case runtime caused by a regex being moved across the input string. The reported cases are a problem because the super-linear worst-case runtime can be exploited by attackers in what is called Regular expression Denial of Service - ReDoS.

## Examples

```js
/* eslint regexp/no-super-linear-move: "error" */
/* ✓ GOOD */
var foo = /abc|def/;
var foo = /\ba+b/;
var foo = /^\s*foo:/;
var foo = /ab+/;
var foo = /#.*/;

/* ✗ BAD */
var foo = /a+b/;
var foo = /^\s*foo:/m;
var foo = /<.*?>/;
```
