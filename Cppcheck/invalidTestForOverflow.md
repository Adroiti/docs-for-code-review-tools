Pattern: Invalid test for overflow

Issue: -

## Description

Invalid test for overflow `x + u < x`. Condition is always false unless there is overflow, and overflow is UB.

## Further Reading

* [Common Weakness Enumeration (CWE) - 570](https://cwe.mitre.org/data/definitions/570.html)