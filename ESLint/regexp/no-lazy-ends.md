Pattern: Lazy quantifier at pattern end

Issue: -

## Description

If a lazily quantified element is the last element matched by an expression (e.g. the `a{2,3}?` in `b+a{2,3}?`), we know that the lazy quantifier will always only match the element the minimum number of times. The maximum is completely ignored because the expression can accept after the minimum was reached.

If the minimum of the lazy quantifier is 0, we can even remove the quantifier and the quantified element without changing the meaning of the pattern. E.g. `a+b*?` and `a+` behave the same.

## Examples

```js
/* eslint regexp/no-lazy-ends: "error" */
/* ✓ GOOD */
var foo = /a+?b*/
var foo = /a??(?:ba+?|c)*/
var foo = /ba*?$/

/* ✗ BAD */
var foo = /a??/
var foo = /a+b+?/
var foo = /a(?:c|ab+?)?/
```
