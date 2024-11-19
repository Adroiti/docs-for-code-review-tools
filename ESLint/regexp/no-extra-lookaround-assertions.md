Pattern: Unnecessary nested lookaround assertion

Issue: -

## Description

The last positive lookahead assertion within a lookahead assertion is the same without lookahead assertions.
Also, The first positive lookbehind assertion within a lookbehind assertion is the same without lookbehind assertions.
They can be inlined or converted to group.

## Examples

```js
/* eslint regexp/no-extra-lookaround-assertions: "error" */
/* ✓ GOOD */
var ts = 'JavaScript'.replace(/Java(?=Script)/u, 'Type');
var java = 'JavaScript'.replace(/(?<=Java)Script/u, '');

/* ✗ BAD */
var ts = 'JavaScript'.replace(/Java(?=Scrip(?=t))/u, 'Type');
var java = 'JavaScript'.replace(/(?<=(?<=J)ava)Script/u, '');
```
