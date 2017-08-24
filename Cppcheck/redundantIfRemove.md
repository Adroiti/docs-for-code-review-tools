Pattern: Redundant STL container check

Issue: -

## Description

Redundant checking of STL container element existence before removing it. It is safe to call the remove method on a non-existing element.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)