Pattern: Unnecessary non-capturing group

Issue: -

## Description

This rule reports unnecessary non-capturing groups. Unnecessary groups are just clutter that make regexes harder to read, so they should be removed.

## Examples

```js
/* eslint regexp/no-useless-non-capturing-group: "error" */
/* ✓ GOOD */
var foo = /(?:abcd)?/
var foo = /a(?:ab|cd)/

/* ✗ BAD */
var foo = /(?:ab|cd)/
var foo = /(?:abcd)/
var foo = /(?:[a-d])/
var foo = /(?:[a-d])|e/
var foo = /(?:a|(?:b|c)|d)/
```
