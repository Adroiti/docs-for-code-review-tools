Pattern: Comparison of func returning bool error

Issue: -

## Description

The return type of function `func_name` is `bool` and result is of type `bool`. Comparing `bool` value using relational (<, >, <= or >=) operator could cause unexpected results.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)