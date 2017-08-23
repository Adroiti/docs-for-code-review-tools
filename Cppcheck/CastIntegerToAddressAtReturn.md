Pattern: Cast integer to address at return

Issue: -

## Description

Returning an integer (int/long/etc) in a function with pointer return type is not portable across different platforms and compilers. For example in 32-bit Windows and Linux they are same width, but in 64-bit Windows and Linux they are of different width. In worst case you end up casting 64-bit integer down to 32-bit pointer. The safe way is to always return a pointer.

## Further Reading

* [Common Weakness Enumeration (CWE) - 758](https://cwe.mitre.org/data/definitions/758.html)