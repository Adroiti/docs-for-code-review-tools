Pattern: Missing use of using result array `groups`

Issue: -

## Description

This rule reports and fixes regexp result arrays where named capturing groups are accessed by index instead of using the `groups` property.

## Examples

```js
/* eslint regexp/prefer-result-array-groups: "error" */

const regex = /(?<foo>a)(b)c/g
let match
while (match = regex.exec(str)) {
    /* ✓ GOOD */
    var p1 = match.groups.foo
    var p2 = match[2]

    /* ✗ BAD */
    var p1 = match[1]
}

```
