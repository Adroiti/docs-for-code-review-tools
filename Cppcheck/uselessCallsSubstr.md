Pattern: Ineffective call of `string::substr()`

Issue: -

## Description

Ineffective call of function `string::substr()` because it returns a copy of the object. Use `=` instead.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)