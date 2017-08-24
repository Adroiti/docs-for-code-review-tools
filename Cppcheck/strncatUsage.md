Pattern: Unsafe use of `strncat()` usage

Issue: -

## Description

At most, `strncat()` appends the 3rd parameter’s amount of characters and adds a terminating null byte.
The safe way to use `strncat()` is to subtract one from the remaining space in the buffer and use it as 3rd parameter.

## Further Reading

* [Common Weakness Enumeration (CWE) - 119](https://cwe.mitre.org/data/definitions/119.html)
* [The C++ Resources Network - strncat](http://www.cplusplus.com/reference/cstring/strncat/)