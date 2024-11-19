Pattern: Empty lookahead or lookbehind assertion

Issue: -

## Description

This rule reports empty lookahead assertion or empty lookbehind assertion.

An empty lookaround is a lookaround for which at least one path in the lookaround expression contains only elements that do not consume characters and do not assert characters. This means that the lookaround expression will trivially accept any input string.

## Examples

```js
/* eslint regexp/no-empty-lookaround-assertion: "error" */
/* ✓ GOOD */
var foo = /x(?=y)/;
var foo = /x(?!y)/;
var foo = /(?<=y)x/;
var foo = /(?<!y)x/;

/* ✗ BAD */
var foo = /x(?=)/;
var foo = /x(?!)/;
var foo = /(?<=)x/;
var foo = /(?<!)x/;
```
