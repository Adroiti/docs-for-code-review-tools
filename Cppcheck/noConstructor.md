Pattern: Class with no constructor

Issue: -

## Description

Class does not have a constructor although it has private member variables. Member variables of builtin types are left uninitialized when the class is instantiated. That may cause bugs or undefined behavior.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)