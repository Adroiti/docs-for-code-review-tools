Pattern: Element contradicting an assertion

Issue: -

## Description

This rule reports elements that contradict an assertion. All elements reported by this rule fall into one of two categories:

1. An element/alternative that can never be entered.
    This means that the element is dead code and can be removed.

2. An element that is always entered.
    Right now, only quantifiers with a minimum of 0 are reported in this category. They are contradictory because the minimum of 0 is changed by the assertion to be effectively 1.

## Examples

```js
/* eslint regexp/no-contradiction-with-assertion: "error" */
/* ✓ GOOD */
var foo = /a\b-a/;
var foo = /a\ba/;

/* ✗ BAD */
var foo = /a\b-?a/;
var foo = /a\b(a|-)/;
var foo = /a\ba*-/;
```
