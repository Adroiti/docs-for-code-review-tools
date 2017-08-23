Pattern: Malloc on class warning

Issue: -

## Description

Memory for class instance allocated with malloc(), but class provides constructors. This is unsafe, since no constructor is called and class members remain uninitialized. Consider using `new` instead.

## Further Reading

* [Common Weakness Enumeration (CWE) - 762](https://cwe.mitre.org/data/definitions/762.html)