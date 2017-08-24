Pattern: Clarify calculation

Issue: -

## Description

Suspicious calculation. Please use parentheses to clarify the code. The code ``a+b?c:d`` should be written as either `(a+b)?c:d` or `a+(b?c:d)`.

## Further Reading

* [Common Weakness Enumeration (CWE) - 783](https://cwe.mitre.org/data/definitions/783.html)