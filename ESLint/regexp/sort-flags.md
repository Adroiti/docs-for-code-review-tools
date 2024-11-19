Pattern: Unsorted flags in regular expression

Issue: -

## Description

The flags of JavaScript regular expressions should be sorted alphabetically because the flags of the `.flags` property of `RegExp` objects are always sorted. Not sorting flags in regex literals misleads readers into thinking that the order may have some purpose which it doesn't.

## Examples

```js
/* eslint regexp/sort-flags: "error" */
/* ✓ GOOD */
var foo = /abc/
var foo = /abc/iu
var foo = /abc/gimsuy

/* ✗ BAD */
var foo = /abc/mi
var foo = /abc/us
```
