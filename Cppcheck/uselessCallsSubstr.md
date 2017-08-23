Pattern: Useless calls substr

Issue: -

## Description

Ineffective call of function `substr` because it returns a copy of the object. Use operator= instead.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)