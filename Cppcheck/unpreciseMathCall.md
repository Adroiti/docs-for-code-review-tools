Pattern: Imprecise math call

Issue: -

## Description

Expression `1 - erf(x)` can be replaced by `erfc(x)` to avoid loss of precision.

## Further Reading

* [Common Weakness Enumeration (CWE) - 758](https://cwe.mitre.org/data/definitions/758.html)