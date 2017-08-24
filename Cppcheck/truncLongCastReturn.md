Pattern: `int` result is returned as `long` value

Issue: -

## Description

`int` result is returned as `long` value. If the return value is `long` to avoid loss of information, then there is loss of information. To avoid loss of information you must cast a calculation operand to `long`, for example `return a*b;` => `return (long)a*b`.

## Further Reading

* [Common Weakness Enumeration (CWE) - 197](https://cwe.mitre.org/data/definitions/197.html)