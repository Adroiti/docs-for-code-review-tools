Pattern: Dangerous use of `c_str()`

Issue: -

## Description

Dangerous usage of `c_str()`. The `c_str()` return value is only valid until its string is deleted.

## Further Reading

* [Common Weakness Enumeration (CWE) - 664](https://cwe.mitre.org/data/definitions/664.html)