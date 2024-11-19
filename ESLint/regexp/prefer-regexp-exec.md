Pattern: Missing use of `RegExp#exec`

Issue: -

## Description

This rule enforces the use of the more performant way of applying regular expressions on strings. `RegExp#exec` is faster than `String#match` and both work the same when not using the `/g` flag.

## Examples

```js
/* eslint regexp/prefer-regexp-exec: "error" */

/* ✓ GOOD */
/thing/.exec('something');

'some things are just things'.match(/thing/g);

const text = 'something';
const search = /thing/;
search.exec(text);

/* ✗ BAD */
'something'.match(/thing/);

'some things are just things'.match(/thing/);

text.match(search);

```
