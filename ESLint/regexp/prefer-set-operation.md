Pattern: Missing use of character class set operation

Issue: -

## Description

Regular expressions with the `v` flag have access to character class set operations (e.g. `/[\s&&\p{ASCII}]/v`, `/[\w--\d]/v`). These are more readable and performant than using lookarounds to achieve the same effect.

## Examples

```js
/* eslint regexp/prefer-set-operation: "error" */
/* ✓ GOOD */
var foo = /(?!\d)\w/  // requires the v flag
var foo = /(?!\d)\w/u // requires the v flag

/* ✗ BAD */
var foo = /(?!\d)\w/v
var foo = /(?!\s)[\w\P{ASCII}]/v
```
