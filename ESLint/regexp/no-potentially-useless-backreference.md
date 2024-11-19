Pattern: Backreference that might reference an unmatched group

Issue: -

## Description

If the referenced group of a backreference is not matched because some other path leads to the backreference, the backreference will trivially accept (e.g. `/(?:(a)|b)\1/`). The same will happen if the captured text of the referenced group was reset before reaching the backreference.

This will not handle backreferences that always trivially accept. Use `regexp/no-useless-backreference` for that.

## Examples

```js
/* eslint regexp/no-potentially-useless-backreference: "error" */
/* ✓ GOOD */
var foo = /(a+)b\1/;
var foo = /(a+)b|\1/;  // this will be done by regexp/no-useless-backreference

/* ✗ BAD */
var foo = /(?:(a)|b)\1/;
var foo = /(a)?b\1/;
var foo = /((a)|c)+b\2/;
```
