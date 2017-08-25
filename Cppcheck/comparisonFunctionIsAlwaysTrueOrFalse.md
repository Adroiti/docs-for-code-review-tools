Pattern: Comparison of two identical variables

Issue: -

## Description

Comparison of two identical variables with `isless(varName,varName)` always evaluates to false.

The function `isless` is designed to compare two variables. Calling this function with one variable for both parameters leads to a statement which is always true or false.

## Further Reading

* [Common Weakness Enumeration (CWE) - 570](https://cwe.mitre.org/data/definitions/570.html)