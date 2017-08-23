Pattern: Clarify statement

Issue: -

## Description

A statement like `*A++;` might not do what you intended. Postfix `operator++` is executed before `operator*`. Thus, the dereference is meaningless. Did you intend to write `(*A)++;`?

## Further Reading

* [Common Weakness Enumeration (CWE) - 783](https://cwe.mitre.org/data/definitions/783.html)