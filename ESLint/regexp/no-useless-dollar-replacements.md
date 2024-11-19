Pattern: Unnecessary `$` replacement in replacement string

Issue: -

## Description

This rule aims to detect and disallow useless `$` replacements in regular expression replacements.

## Examples

```js
/* eslint regexp/no-useless-dollar-replacements: "error" */
/* ✓ GOOD */
var newStr = str.replace(/(\w+)\s(\w+)/, '$2, $1');
var newStr = str.replace(/(?<first>\w+)\s(?<last>\w+)/, '$<last>, $<first>');
'123456789012'.replaceAll(/(.)../g, '$1**');

/* ✗ BAD */
var newStr = str.replace(/(\w+)\s(\w+)/, '$3, $1 $2');
var newStr = str.replace(/(?<first>\w+)\s(?<last>\w+)/, '$<last>, $<first> $<middle>');
var newStr = str.replace(/(\w+)\s(\w+)/, '$<last>, $<first>');
```
