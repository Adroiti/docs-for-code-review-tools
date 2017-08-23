Pattern: Array index then check

Issue: -

## Description

Defensive programming: The variable `index` is used as an array index before it is checked that is within limits. This can mean that the array might be accessed out of bounds. Reorder conditions such as `(a[i] && i < 10)` to `(i < 10 && a[i])`. That way the array will not be accessed if the index is out of limits.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)