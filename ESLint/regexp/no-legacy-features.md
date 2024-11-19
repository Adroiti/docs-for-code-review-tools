Pattern: Use of legacy RegExp feature

Issue: -

## Description

This rule disallows legacy RegExp features.

## Examples

```js
/* eslint regexp/no-legacy-features: "error" */
/* ✗ BAD */
RegExp.input
RegExp.$_
RegExp.lastMatch
RegExp["$&"]
RegExp.lastParen
RegExp["$+"]
RegExp.leftContext
RegExp["$`"]
RegExp.rightContext
RegExp["$'"]
RegExp.$1
RegExp.$2

const regexObj = new RegExp('foo', 'gi');
regexObj.compile('new foo', 'g');
```
