Pattern: Duplicate break

Issue: -

## Description

Consecutive return, break, continue, goto or throw statements are unnecessary. The second statement can never be executed, and so should be removed.

## Further Reading

* [Common Weakness Enumeration (CWE) - 561](https://cwe.mitre.org/data/definitions/561.html)