Pattern: Redundant copy for local `const`

Issue: -

## Description

The `const` variable is assigned a copy of the data. You can avoid the unnecessary data copying by converting to const reference.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)