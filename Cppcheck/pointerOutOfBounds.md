Pattern: Pointer out of bounds

Issue: -

## Description

Pointer arithmetic is out of bounds. From chapter 6.5.6 in the C specification:

> If both the pointer operand and the result point to elements of the same array object, or one past the last element of the array object, the evaluation shall not produce an overflow; otherwise, the behavior is undefined.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)