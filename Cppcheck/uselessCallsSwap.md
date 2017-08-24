Pattern: Redundant `swap()` call

Issue: -

## Description

The `swap()` function has no logical effect when given itself as parameter (`str.swap(str)`).

## Further Reading

* [Common Weakness Enumeration (CWE) - 628](https://cwe.mitre.org/data/definitions/628.html)