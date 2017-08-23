Pattern: Cstyle cast

Issue: -

## Description

C-style pointer casting detected. C++ offers four different kinds of casts as replacements: static_cast, const_cast, dynamic_cast and reinterpret_cast. A C-style cast could evaluate to any of those automatically, thus it is considered safer if the programmer explicitly states which kind of cast is expected. See also: https://www.securecoding.cert.org/confluence/display/cplusplus/EXP05-CPP.+Do+not+use+C-style+casts.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)