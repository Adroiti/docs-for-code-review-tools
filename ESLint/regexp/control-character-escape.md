Pattern: Unescaped or inconsistent control character

Issue: -

## Description

This rule reports control characters that were not escaped using a control escape (`\0`, `\t`, `\n`, `\v`, `\f`, `\r`).

## Examples

```js
/* eslint regexp/control-character-escape: "error" */
/* ✓ GOOD */
var foo = /[\n\r]/;
var foo = /\t/;
var foo = RegExp("\t+\n");

/* ✗ BAD */
var foo = /	/;
var foo = /\u0009/;
var foo = /\u{a}/u;
var foo = RegExp("\\u000a");
```
