Pattern: Malloc on class error

Issue: -

## Description

Memory for class instance allocated with `malloc()`, but class a std::string. This is unsafe, since no constructor is called and class members remain uninitialized. Consider using `new` instead.

## Further Reading

* [Common Weakness Enumeration (CWE) - 665](https://cwe.mitre.org/data/definitions/665.html)