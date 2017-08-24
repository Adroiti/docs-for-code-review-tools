Pattern: Use of `auto_ptr` for pointers obtained with `malloc`

Issue: -

## Description

Object pointed by an `auto_ptr` is destroyed using operator `delete`. You should not use `auto_ptr` for pointers obtained with function `malloc`. This means that you should only use `auto_ptr` for pointers obtained with operator `new`. This excludes use C library allocation functions (for example `malloc`), which must be deallocated by the appropriate C library function.

## Further Reading

* [Common Weakness Enumeration (CWE) - 762](https://cwe.mitre.org/data/definitions/762.html)