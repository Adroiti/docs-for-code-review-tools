Pattern: Bad bitmask check

Issue: -

## Description

Result of operator `|` is always true if one operand is non-zero. Did you intend to use `&`?

## Further Reading

* [Common Weakness Enumeration (CWE) - 571](https://cwe.mitre.org/data/definitions/571.html)