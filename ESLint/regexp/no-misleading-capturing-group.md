Pattern: Misleading capturing group

Issue: -

## Description

This rule reports capturing groups that capture less text than their pattern might suggest.

E.g. in `/a+(a*)/`, `(a*)` will **always** capture 0 characters because all `a`s are already consumed by `a+`. This is quite surprising behavior because `a*` suggests that the capturing group captures as many `a`s as possible.

## Examples

```js
/* eslint regexp/no-misleading-capturing-group: "error" */
/* ✓ GOOD */
var foo = /a+(b*)/

/* ✗ BAD */
var foo = /a+(a*)/
var foo = /\w+(\d*)/
var foo = /^(a*).+/
```
