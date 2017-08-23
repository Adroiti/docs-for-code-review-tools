Pattern: Pointer arith bool

Issue: -

## Description

Converting pointer arithmetic result to bool. The boolean result is always true unless there is pointer arithmetic overflow, and overflow is undefined behaviour. Probably a dereference is forgotten.

## Further Reading

* [Common Weakness Enumeration (CWE) - 571](https://cwe.mitre.org/data/definitions/571.html)