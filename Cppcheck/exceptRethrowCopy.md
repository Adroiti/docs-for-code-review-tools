Pattern: Rethrowing with copy

Issue: -

## Description

Rethrowing an exception with `throw varname;` creates an unnecessary copy of `varname`. To rethrow the caught exception without unnecessary copying or slicing, use a bare `throw;`.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)