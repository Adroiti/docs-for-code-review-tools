Pattern: Member variable in wrong place in initializer list

Issue: -

## Description

Members are initialized in the order they are declared, not in the order they are in the initializer list.  Keeping the initializer list in the same order that the members were declared prevents order dependent initialization errors.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)