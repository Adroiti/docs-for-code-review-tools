Pattern: Memset zero bytes

Issue: -

## Description

`memset()` called to fill 0 bytes. The second and third arguments might be inverted. The function memset ( void * ptr, int value, size_t num ) sets the first num bytes of the block of memory pointed by ptr to the specified value.

## Further Reading

* [Common Weakness Enumeration (CWE) - 687](https://cwe.mitre.org/data/definitions/687.html)