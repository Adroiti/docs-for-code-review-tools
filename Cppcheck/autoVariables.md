Pattern: Local auto-variable assigned to function parameter

Issue: -

## Description

Dangerous assignment - the function parameter is assigned the address of a local auto-variable. Local auto-variables are reserved from the stack which is freed when the function ends. So the pointer to a local variable is invalid after the function ends.

## Further Reading

* [Common Weakness Enumeration (CWE) - 562](https://cwe.mitre.org/data/definitions/562.html)