Pattern: Use of capturing group where lookaround would suffice

Issue: -

## Description

This rule reports string replacement using capturing groups that can be replaced with lookaround assertions.

## Examples

```js
/* eslint regexp/prefer-lookaround: "error" */
/* ✓ GOOD */
var str = 'JavaScript'.replace(/Java(?=Script)/g, 'Type')

/* ✗ BAD */
var str = 'JavaScript'.replace(/Java(Script)/g, 'Type$1')
```
