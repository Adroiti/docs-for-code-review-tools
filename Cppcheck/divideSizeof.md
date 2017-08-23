Pattern: Divide sizeof

Issue: -

## Description

Division of result of `sizeof()` on pointer type. `sizeof()` returns the size of the pointer, not the size of the memory area it points to.

## Further Reading

* [Common Weakness Enumeration (CWE) - 682](https://cwe.mitre.org/data/definitions/682.html)