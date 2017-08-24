Pattern: Missing `va_end()`

Issue: -

## Description

`va_start()` or `va_copy()` called subsequently without `va_end()` in between.

## Further Reading

* [Common Weakness Enumeration (CWE) - 664](https://cwe.mitre.org/data/definitions/664.html)