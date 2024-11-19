Pattern: Unnecessarily nested assertion

Issue: -

## Description

Lookaround assertions that only contain another assertion can be simplified.

## Examples

```js
/* eslint regexp/no-trivially-nested-assertion: "error" */
/* ✓ GOOD */
var foo = /a(?=b)/;
var foo = /a(?!$)/;

/* ✗ BAD */
var foo = /a(?=$)/;
var foo = /a(?=(?!a))/;
```
