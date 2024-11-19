Pattern: Character class with single character

Issue: -

## Description

This rule reports character classes that defines only one character.

Character classes that define only one character have the same effect even if you remove the brackets.

## Examples

```js
/* eslint regexp/no-useless-character-class: "error" */
/* ✓ GOOD */
var foo = /abc/;

/* ✗ BAD */
var foo = /a[b]c/;
```
