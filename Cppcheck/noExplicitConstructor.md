Pattern: Class constructor not explicit

Issue: -

## Description

Class has a constructor that is not explicit. Such constructors should in general be explicit for type safety reasons. Using the `explicit` keyword in the constructor means some mistakes when using the class can be avoided.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)