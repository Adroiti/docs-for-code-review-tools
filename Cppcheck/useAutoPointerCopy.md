Pattern: Use of `auto_ptr` copy

Issue: -

## Description


Copying `auto_ptr` pointer to another does not create two equal objects since one has lost its ownership of the pointer.

`std::auto_ptr` has semantics of strict ownership, meaning that the `auto_ptr` instance is the sole entity responsible for the object’s lifetime. If an `auto_ptr` is copied, the source looses the reference.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)