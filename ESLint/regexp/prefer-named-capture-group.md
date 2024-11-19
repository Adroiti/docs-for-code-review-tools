Pattern: Unnamed capturing group

Issue: -

## Description

This rule reports capturing groups without a name.

This rule is inspired by the `prefer-named-capture-group` rule. The positions of reports are improved over the core rule and arguments of `new RegExp()` are also checked.

## Examples

```js
/* eslint regexp/prefer-named-capture-group: "error" */
/* ✓ GOOD */
var foo = /(?<foo>ba+r)/;
var foo = /\b(?:foo)+\b/;

/* ✗ BAD */
var foo = /\b(foo)+\b/;
```
