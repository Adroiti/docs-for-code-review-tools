Pattern: Invalid `scanf()` format width

Issue: -

## Description

Width given in format string is larger than destination buffer, use `%-1s` to prevent overflowing it.

## Further Reading

* [Common Weakness Enumeration (CWE) - 687](https://cwe.mitre.org/data/definitions/687.html)