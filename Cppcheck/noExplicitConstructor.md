Pattern: No explicit constructor

Issue: -

## Description

Class `classname` has a constructor with 1 argument that is not explicit. Such constructors should in general be explicit for type safety reasons. Using the explicit keyword in the constructor means some mistakes when using the class can be avoided.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)