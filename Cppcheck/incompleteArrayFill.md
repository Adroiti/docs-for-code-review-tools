Pattern: Incomplete array fill

Issue: -

## Description

The array `buffer` is filled incompletely. The function `memset()` needs the size given in bytes, but an element of the given array is larger than one byte. Did you forget to multiply the size with `sizeof(*buffer)`?

## Further Reading

* [Common Weakness Enumeration (CWE) - 131](https://cwe.mitre.org/data/definitions/131.html)