Pattern: Useless calls swap

Issue: -

## Description

The `swap()` function has no logical effect when given itself as parameter (str.swap(str)). As it is currently the code is inefficient. Is the object or the parameter wrong here?

## Further Reading

* [Common Weakness Enumeration (CWE) - 628](https://cwe.mitre.org/data/definitions/628.html)