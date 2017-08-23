Pattern: Race after interlocked decrement

Issue: -

## Description

Race condition: non-interlocked access after `InterlockedDecrement()`. Use `InterlockedDecrement()` return value instead.

## Further Reading

* [Common Weakness Enumeration (CWE) - 362](https://cwe.mitre.org/data/definitions/362.html)