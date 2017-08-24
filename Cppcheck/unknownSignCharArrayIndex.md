Pattern: `char` type used as array index

Issue: -

## Description

`char` type used as array index. Values greater that 127 will be treated depending on whether `char` is signed or unsigned on target platform.

## Further Reading

* [Common Weakness Enumeration (CWE) - 758](https://cwe.mitre.org/data/definitions/758.html)