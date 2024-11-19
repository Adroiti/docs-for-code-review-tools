Pattern: Misleading Unicode character

Issue: -

## Description

Some Unicode characters like '❇️', '🏴‍☠️', and '👨‍👩‍👦' consist of multiple code points. This causes problems in character classes and around quantifiers. E.g.

```js
> /^[❇️🏴‍☠️]$/.test("🏴‍☠️")
false
> /^👨‍👩‍👦{2,4}$/.test("👨‍👩‍👦👨‍👩‍👦")
false
```

## Examples

```js
/* eslint regexp/no-misleading-unicode-character: "error" */
/* ✓ GOOD */
var foo = /👍+/u;
var foo = /👨‍👩‍👦/;

/* ✗ BAD */
var foo = /👍+/;
var foo = /[❇️🏴‍☠️👨‍👩‍👦]❤️/;
```
