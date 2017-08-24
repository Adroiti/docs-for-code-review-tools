Pattern: Use of unsafe class

Issue: -

## Description

The class is unsafe, wrong usage can cause memory/resource leaks. This can for instance be fixed by adding proper cleanup in the destructor.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)