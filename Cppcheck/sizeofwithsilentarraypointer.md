Pattern: Sizeofwithsilentarraypointer

Issue: -

## Description

Using `sizeof` for array given as function argument returns the size of a pointer. It does not return the size of the whole array in bytes as might be expected. For example, this code:
     int f(char a[100]) {
         return sizeof(a);
     }
returns 4 (in 32-bit systems) or 8 (in 64-bit systems) instead of 100 (the size of the array in bytes).

## Further Reading

* [Common Weakness Enumeration (CWE) - 467](https://cwe.mitre.org/data/definitions/467.html)