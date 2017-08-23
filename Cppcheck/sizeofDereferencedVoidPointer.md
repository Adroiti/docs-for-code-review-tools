Pattern: Sizeof dereferenced void pointer

Issue: -

## Description

`*varname` is of type `void`, the behaviour of `sizeof(void)` is not covered by the ISO C standard. A value for `sizeof(void)` is defined only as part of a GNU C extension, which defines `sizeof(void)` to be 1.

## Further Reading

* [Common Weakness Enumeration (CWE) - 682](https://cwe.mitre.org/data/definitions/682.html)