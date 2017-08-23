Pattern: Invalid scanf format width

Issue: -

## Description

Width 5 given in format string (no. 10) is larger than destination buffer `[0]`, use %-1s to prevent overflowing it.

## Further Reading

* [Common Weakness Enumeration (CWE) - 687](https://cwe.mitre.org/data/definitions/687.html)