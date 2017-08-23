Pattern: Use auto pointer array

Issue: -

## Description

Object pointed by an `auto_ptr` is destroyed using operator `delete`. This means that you should only use `auto_ptr` for pointers obtained with operator `new`. This excludes arrays, which are allocated by operator `new[]` and must be deallocated by operator `delete[]`.

## Further Reading

* [Common Weakness Enumeration (CWE) - 664](https://cwe.mitre.org/data/definitions/664.html)