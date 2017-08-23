Pattern: Sizeof division memfunc

Issue: -

## Description

Division by result of `sizeof()`. `memset()` expects a size in bytes, did you intend to multiply instead?

## Further Reading

* [Common Weakness Enumeration (CWE) - 682](https://cwe.mitre.org/data/definitions/682.html)