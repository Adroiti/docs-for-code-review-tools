Pattern: Unnecessary operand in expression character class

Issue: -

## Description

The `v` flag added set operations for character classes, e.g. `[\w&&\D]` and `[\w--\d]`, but there are no limitations on what operands can be used. This rule reports any unnecessary operands.

## Examples

```js
/* eslint regexp/no-useless-set-operand: "error" */
/* ✓ GOOD */
foo = /[\w--\d]/v
foo = /[\w--[\d_]]/v

/* ✗ BAD */
foo = /[\w--[\d$]]/v
foo = /[\w&&\d]/v
foo = /[\w&&\s]/v
foo = /[\w&&[\d\s]]/v
```
