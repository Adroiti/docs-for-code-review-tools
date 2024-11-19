Pattern: Inconsistent Unicode property naming

Issue: -

## Description

This rule helps to enforce consistent style and naming of Unicode properties. There are many ways a single Unicode property can be expressed. E.g. `\p{L}`, `\p{Letter}`, `\p{gc=L}`, `\p{gc=Letter}`, `\p{General_Category=L}`, and `\p{General_Category=Letter}` are all equivalent.

## Examples

```js
/* eslint regexp/unicode-property: "error" */
/* ✓ GOOD */
var re = /\p{L}/u;
var re = /\p{Letter}/u;
var re = /\p{Script=Greek}/u;
var re = /\p{Hex}/u;

/* ✗ BAD */
var re = /\p{gc=L}/u;
var re = /\p{General_Category=Letter}/u;
var re = /\p{Script=Grek}/u;
```
