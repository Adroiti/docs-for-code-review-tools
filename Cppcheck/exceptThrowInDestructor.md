Pattern: Except throw in destructor

Issue: -

## Description

The class is not safe because its destructor throws an exception. If Class is used and an exception is thrown that is caught in an outer scope the program will terminate.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)