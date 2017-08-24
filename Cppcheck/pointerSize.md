Pattern: Size of pointer used instead of size of its data

Issue: -

## Description

Size of pointer used instead of size of its data. This is likely to lead to a buffer overflow. You probably intend to write `sizeof(*varname)`.

## Further Reading

* [Common Weakness Enumeration (CWE) - 467](https://cwe.mitre.org/data/definitions/467.html)