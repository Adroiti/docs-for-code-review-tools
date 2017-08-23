Pattern: Comparison error

Issue: -

## Description

The expression `(X & 0x6) == 0x1` is always false. Check carefully constants and operators used, these errors might be hard to spot sometimes. In case of complex expression it might help to split it to separate expressions.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)