Pattern: Memset class float

Issue: -

## Description

Using memset() on class which contains a floating point number. This is not portable because memset() sets each byte of a block of memory to a specific value and the actual representation of a floating-point value is implementation defined. Note: In case of an IEEE754-1985 compatible implementation setting all bits to zero results in the value 0.0.

## Further Reading

* [Common Weakness Enumeration (CWE) - 758](https://cwe.mitre.org/data/definitions/758.html)