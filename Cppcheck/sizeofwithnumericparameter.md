Pattern: Suspicious use `sizeof` with numeric constant

Issue: -

## Description

Suspicious usage of `sizeof` with a numeric constant as parameter. It is unusual to use a constant value with `sizeof`. For example, `sizeof(10)` returns 4 (in 32-bit systems) or 8 (in 64-bit systems) instead of 10. `sizeof(A)` and `sizeof(char)` can return different results.

## Further Reading

* [Common Weakness Enumeration (CWE) - 682](https://cwe.mitre.org/data/definitions/682.html)