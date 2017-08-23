Pattern: Copy ctor pointer copying

Issue: -

## Description

Value of pointer `var`, which points to allocated memory, is copied in copy constructor instead of allocating new memory.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)