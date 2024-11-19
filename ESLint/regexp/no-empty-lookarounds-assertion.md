Pattern: Empty lookaround assertion

Issue: -

## Description

This rule reports empty lookaround assertions that will trivially accept or reject any input string.

An empty lookaround is a lookaround for which at least one path in the lookaround expression contains only elements that do not consume characters and do not assert characters. This means that the lookaround expression will trivially accept any input string.

## Examples

```js
/* eslint regexp/no-empty-lookarounds-assertion: "error" */

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
var foo = /(?=b?)\w/;
var foo = /(?!b?)\w/;

```
