Pattern: Possible out of bounds buffer access

Issue: -

## Description

Possible buffer overflow if `strlen(source)` is larger than or equal to `sizeof(destination)`. The source buffer is larger than the destination buffer so there is the potential for overflowing the destination buffer.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)