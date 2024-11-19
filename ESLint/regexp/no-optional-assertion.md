Pattern: Optional assertion that serves no purpose

Issue: -

## Description

Assertions that are quantified (directly or indirectly) can be considered optional if the quantifier has a minimum of zero.

A simple example is the following pattern: `/a(?:$)*b/`. The `$` assertion will reject, but if that happens it will simply be ignored because of the `*` quantifier. The assertion is optional, serving no function whatsoever.

More generally, an assertion is optional, if there exists a parent quantifier with a minimum of zero such that all possible paths of the quantified element that contain the assertion do not consume characters.

## Examples

```js
/* eslint regexp/no-optional-assertion: "error" */
/* ✓ GOOD */
var foo = /\w+(?::|\b)/;

/* ✗ BAD */
var foo = /a(?:$)*b/;
var foo = /a(?:foo|(?<!-)(?:-|\b))*b/; // The \b is optional
var foo = /(?:^)?\w+/;   // warns about ^
var foo = /\w+(?::|$)?/; // warns about $
```
