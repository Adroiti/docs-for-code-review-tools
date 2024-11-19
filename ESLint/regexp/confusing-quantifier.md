Pattern: Quantifier that implies incorrect matching behavior

Issue: -

## Description

Confusing quantifiers are ones which imply one thing but don't deliver on that.

An example of this is `(?:a?b*|c+){4}`. The group is quantified with `{4}` which implies that at least 4 characters will be matched, but this is not the case. The whole pattern will match the empty string. It does that because in the `a?b*` alternative, it's possible to choose 0 many `a` and `b`. So rather than `{4}`, `{0,4}` should be used to reflect the fact that the empty string can be matched.

## Examples

```js
/* eslint regexp/confusing-quantifier: "error" */
/* ✓ GOOD */
var foo = /a*/;
var foo = /(a|b|c)+/;
var foo = /a?/;

/* ✗ BAD */
var foo = /(a?){4}/; // warns about `{4}`
var foo = /(a?b*)+/; // warns about `+`
```
