Pattern: Redundant copy in switch

Issue: -

## Description

Buffer `var` is being written before its old content has been used. `break;` missing?

## Further Reading

* [Common Weakness Enumeration (CWE) - 563](https://cwe.mitre.org/data/definitions/563.html)