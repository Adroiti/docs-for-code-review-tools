Pattern: Operator eq to self

Issue: -

## Description

`operator=` should check for assignment to self to ensure that each block of dynamically allocated memory is owned and managed by only one instance of the class.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)