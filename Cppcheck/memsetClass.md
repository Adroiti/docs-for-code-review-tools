Pattern: Use of `memset` on class 

Issue: -

## Description

Using `memset` on class is unsafe, because constructor, destructor and copy operator calls are omitted. These are necessary for this non-POD type to ensure that a valid object is created.

## Further Reading

* [Common Weakness Enumeration (CWE) - 762](https://cwe.mitre.org/data/definitions/762.html)