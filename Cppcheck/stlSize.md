Pattern: Stl size

Issue: -

## Description

Checking for `list` emptiness might be inefficient. Using list.`empty()` instead of list.`size()` can be faster. list.`size()` can take linear time but list.`empty()` is guaranteed to take constant time.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)