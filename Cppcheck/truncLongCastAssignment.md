Pattern: `int` result is assigned to `long` variable

Issue: -

## Description

`int` result is assigned to `long` variable. If the variable is `long` to avoid loss of information, then there is loss of information. To avoid loss of information you must cast a calculation operand to `long`, for example `l = a * b;` => `l = (long)a * b;`.

## Further Reading

* [Common Weakness Enumeration (CWE) - 197](https://cwe.mitre.org/data/definitions/197.html)