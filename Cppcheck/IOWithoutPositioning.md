Pattern: Without positioning

Issue: -

## Description

Read and write operations without a call to a positioning function (fseek, fsetpos or rewind) or fflush in between result in undefined behaviour.

## Further Reading

* [Common Weakness Enumeration (CWE) - 664](https://cwe.mitre.org/data/definitions/664.html)