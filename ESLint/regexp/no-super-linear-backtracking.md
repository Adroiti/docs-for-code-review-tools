Pattern: Pattern vulnerable to exponential/polynomial backtracking

Issue: -

## Description

This rule reports cases of exponential and polynomial backtracking.

These types of backtracking almost always cause an exponential or polynomial worst-case runtime. This super-linear worst-case runtime can be exploited by attackers in what is called Regular expression Denial of Service - ReDoS.

## Examples

```js
/* eslint regexp/no-super-linear-backtracking: "error" */
/* ✓ GOOD */
var foo = /a*b+a*$/;
var foo = /(?:a+)?/;

/* ✗ BAD */
var foo = /(?:a+)+$/;
var foo = /a*b?a*$/;
var foo = /(?:a|b|c+)*$/;
// not all cases can automatically be fixed
var foo = /\s*(.*?)(?=:)/;
var foo = /.+?(?=\s*=)/;
```
