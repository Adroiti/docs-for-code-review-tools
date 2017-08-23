Pattern: Strncat usage

Issue: -

## Description

At most, strncat appends the 3rd parameter`s amount of characters and adds a terminating null byte.
The safe way to use strncat is to subtract one from the remaining space in the buffer and use it as 3rd parameter.Source: http://www.cplusplus.com/reference/cstring/strncat/
Source: http://www.opensource.apple.com/source/Libc/Libc-167/gen.subproj/i386.subproj/strncat.c

## Further Reading

* [Common Weakness Enumeration (CWE) - 119](https://cwe.mitre.org/data/definitions/119.html)