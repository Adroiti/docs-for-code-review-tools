Pattern: Use of `auto_ptr` container

Issue: -

## Description

You can randomly lose access to pointers if you store `auto_ptr` pointers in an STL container.

An element of container must be able to be copied but `auto_ptr` does not fulfill this requirement. You should consider to use `shared_ptr` or `unique_ptr`. It is suitable for use in containers, because they no longer copy their values, they move them.

## Further Reading

* [Common Weakness Enumeration (CWE) - 664](https://cwe.mitre.org/data/definitions/664.html)