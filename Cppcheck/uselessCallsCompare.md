Pattern: Useless calls compare

Issue: -

## Description

`std::string::find()` returns zero when given itself as parameter (str.find(str)). As it is currently the code is inefficient. It is possible either the string searched (`str`) or searched for (`str`) is wrong.

## Further Reading

* [Common Weakness Enumeration (CWE) - 628](https://cwe.mitre.org/data/definitions/628.html)