Pattern: Return address of function parameter

Issue: -

## Description

Address of the function parameter `parameter` becomes invalid after the function exits because function parameters are stored on the stack which is freed when the function exits. Thus the returned value is invalid.

## Further Reading

* [Common Weakness Enumeration (CWE) - 562](https://cwe.mitre.org/data/definitions/562.html)