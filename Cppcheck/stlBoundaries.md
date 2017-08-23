Pattern: Stl boundaries

Issue: -

## Description

Iterator compared with operator<. This is dangerous since the order of items in the container is not guaranteed. One should use operator!= instead to compare iterators.

## Further Reading

* [Common Weakness Enumeration (CWE) - 664](https://cwe.mitre.org/data/definitions/664.html)