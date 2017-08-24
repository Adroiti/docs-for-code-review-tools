Pattern: Signed `char` used as array index

Issue: -

## Description

Signed `char` type used as array index. If the value can be greater than 127 there will be a buffer underflow because of sign extension.

## Further Reading

* [Common Weakness Enumeration (CWE) - 128](https://cwe.mitre.org/data/definitions/128.html)