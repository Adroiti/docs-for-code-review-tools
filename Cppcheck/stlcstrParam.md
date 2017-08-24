Pattern: Slow `c_str()` argument

Issue: -

## Description

Passing the result of `c_str()` to a function that takes `std::string` as argument no. 0 is slow and redundant. The conversion from const char* as returned by `c_str()` to `std::string` creates an unnecessary string copy. Solve that by directly passing the string.

## Further Reading

* [Common Weakness Enumeration (CWE) - 704](https://cwe.mitre.org/data/definitions/704.html)