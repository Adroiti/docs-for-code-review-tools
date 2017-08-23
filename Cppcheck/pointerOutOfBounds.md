Pattern: Pointer out of bounds

Issue: -

## Description

Undefined behaviour, pointer arithmetic `` is out of bounds. From chapter 6.5.6 in the C specification:
"When an expression that has integer type is added to or subtracted from a pointer, .." and then "If both the pointer operand and the result point to elements of the same array object, or one past the last element of the array object, the evaluation shall not produce an overflow; otherwise, the behavior is undefined."

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)