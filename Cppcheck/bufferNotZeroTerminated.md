Pattern: Buffer not null-terminated

Issue: -

## Description

The buffer is not null-terminated after the call to `strncpy()`. This will cause bugs later in the code if the code assumes the buffer is null-terminated.

## Further Reading

* [Common Weakness Enumeration (CWE) - 170](https://cwe.mitre.org/data/definitions/170.html)