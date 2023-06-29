Pattern: Use of C-style pointer casting

Issue: -

## Description

C++ offers four different kinds of casts as replacements: `static_cast`, `const_cast`, `dynamic_cast` and `reinterpret_cast`. A C-style cast could evaluate to any of those automatically, thus it is considered safer if the programmer explicitly states which kind of cast is expected.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)
