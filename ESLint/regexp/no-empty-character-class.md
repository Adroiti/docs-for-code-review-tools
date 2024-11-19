Pattern: Character class that match no characters

Issue: -

## Description

This rule reports character classes that cannot match any characters.

Character classes that cannot match any characters are either empty or negated character classes of elements that contain all characters.

The reports for this rule include reports for the ESLint core `no-empty-character-class` rule. That is, if you use this rule, you can turn off the ESLint core `no-empty-character-class` rule.

## Examples

```js
/* eslint regexp/no-empty-character-class: "error" */
/* ✓ GOOD */
var foo = /abc[d]/;
var foo = /abc[a-z]/;
var foo = /[^]/;
var foo = /[\s\S]/;

/* ✗ BAD */
var foo = /abc[]/;
var foo = /[^\s\S]/;
```
