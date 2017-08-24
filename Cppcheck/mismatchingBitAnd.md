Pattern: Mismatching bitmasks

Issue: -

## Description

Mismatching bitmasks. Result is always 0 (`X = Y & 0xf0; Z = X & 0x1; => Z=0`).

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)