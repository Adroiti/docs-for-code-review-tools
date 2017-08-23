Pattern: Leak unsafe arg alloc

Issue: -

## Description

Unsafe allocation. If funcName() throws, memory could be leaked. Use make_shared<int>() instead.

## Further Reading

* [Common Weakness Enumeration (CWE) - 401](https://cwe.mitre.org/data/definitions/401.html)