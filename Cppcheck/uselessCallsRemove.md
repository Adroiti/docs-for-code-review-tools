Pattern: Useless calls remove

Issue: -

## Description

The return value of std::remove() is ignored. This function returns an iterator to the end of the range containing those elements that should be kept. Elements past new end remain valid but with unspecified values. Use the erase method of the container to delete them.

## Further Reading

* [Common Weakness Enumeration (CWE) - 762](https://cwe.mitre.org/data/definitions/762.html)