Pattern: Unused capturing group in pattern

Issue: -

## Description

This rule reports unused capturing groups.

Many people use capturing groups instead of non-capturing groups for convenience. However, using capturing groups in place of non-capturing groups can have negative consequences in terms of performance and code clarity.

## Examples

```js
/* eslint regexp/no-unused-capturing-group: "error" */
/* ✓ GOOD */
var replaced = '2000-12-31'.replace(/(\d{4})-(\d{2})-(\d{2})/, '$1/$2/$3')
var matches = '2000-12-31'.match(/(\d{4})-(\d{2})-(\d{2})/)
var y = matches[1]

/* ✗ BAD */
var replaced = '2000-12-31'.replace(/(\d{4})-(\d{2})-(\d{2})/, 'Date')
var isDate = /(\d{4})-(\d{2})-(\d{2})/.test('2000-12-31')
```
