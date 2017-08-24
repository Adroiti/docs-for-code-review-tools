Pattern: `memset()` argument not a float

Issue: -

## Description

The 2nd `memset()` argument is a float, its representation is implementation defined. `memset()` is used to set each byte of a block of memory to a specific value and the actual representation of a floating-point value is implementation defined.

## Further Reading

* [Common Weakness Enumeration (CWE) - 688](https://cwe.mitre.org/data/definitions/688.html)