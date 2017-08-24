Pattern: Saving function return value in `char` variable

Issue: -

## Description

When saving function return value in `char` variable there is loss of precision.  When function returns EOF this value is truncated. Comparing the `char` variable with EOF can have unexpected results. 

For instance a loop `while (EOF != (c = func_name());` loops forever on some compilers/platforms and on other compilers/platforms it will stop when the file contains a matching character.

## Further Reading

* [Common Weakness Enumeration (CWE) - 197](https://cwe.mitre.org/data/definitions/197.html)