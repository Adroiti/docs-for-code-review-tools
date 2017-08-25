Pattern: Deallocation of auto-variable

Issue: -

## Description

The deallocation of an auto-variable results in undefined behaviour. You should only free memory that has been allocated dynamically.

## Further Reading

* [Common Weakness Enumeration (CWE) - 590](https://cwe.mitre.org/data/definitions/590.html)