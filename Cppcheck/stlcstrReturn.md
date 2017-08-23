Pattern: Stlcstr return

Issue: -

## Description

The conversion from const char* as returned by c_str() to std::string creates an unnecessary string copy. Solve that by directly returning the string.

## Further Reading

* [Common Weakness Enumeration (CWE) - 704](https://cwe.mitre.org/data/definitions/704.html)