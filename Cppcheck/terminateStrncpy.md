Pattern: Possibly improper use of `strncpy()`

Issue: -

## Description

If the source string’s size fits or exceeds the given size, `strncpy()` does not add a zero at the end of the buffer. This causes bugs later in the code if the code assumes buffer is null-terminated.

## Further Reading

* [Common Weakness Enumeration (CWE) - 170](https://cwe.mitre.org/data/definitions/170.html)