Pattern: Sizeofsizeof

Issue: -

## Description

Calling sizeof for `sizeof looks like a suspicious code and most likely there should be just one `sizeof`. The current code is equivalent to `sizeof(size_t)`

## Further Reading

* [Common Weakness Enumeration (CWE) - 682](https://cwe.mitre.org/data/definitions/682.html)