Pattern: Unsafe class can leak

Issue: -

## Description

The class `class` is unsafe, wrong usage can cause memory/resource leaks for `class::varname`. This can for instance be fixed by adding proper cleanup in the destructor.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)