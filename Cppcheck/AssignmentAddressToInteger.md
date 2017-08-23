Pattern: Assignment address to integer

Issue: -

## Description

Assigning a pointer to an integer (int/long/etc) is not portable across different platforms and compilers. For example in 32-bit Windows and linux they are same width, but in 64-bit Windows and linux they are of different width. In worst case you end up assigning 64-bit address to 32-bit integer. The safe way is to store addresses only in pointer types (or typedefs like uintptr_t).

## Further Reading

* [Common Weakness Enumeration (CWE) - 758](https://cwe.mitre.org/data/definitions/758.html)