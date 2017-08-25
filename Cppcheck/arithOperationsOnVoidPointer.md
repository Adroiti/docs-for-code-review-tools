Pattern: Arithmetic operation on void pointer

Issue: -

## Description

When using void pointers in calculations, the behaviour is undefined. Arithmetic operations on `void *` is a GNU C extension, which defines the `sizeof(void)` to be 1.

## Further Reading

* [Common Weakness Enumeration (CWE) - 467](https://cwe.mitre.org/data/definitions/467.html)