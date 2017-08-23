Pattern: Memset value out of range

Issue: -

## Description

The 2nd `memset()` argument `varname` doesn`t fit into an `unsigned char`. The 2nd parameter is passed as an `int`, but the function fills the block of memory using the `unsigned char` conversion of this value.

## Further Reading

* [Common Weakness Enumeration (CWE) - 686](https://cwe.mitre.org/data/definitions/686.html)