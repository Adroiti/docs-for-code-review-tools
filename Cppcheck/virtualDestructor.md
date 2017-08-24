Pattern: Missing virtual destructor

Issue: -

## Description

Class `Base` which is inherited by class `Derived` does not have a virtual destructor. If you destroy instances of the derived class by deleting a pointer that points to the base class, only the destructor of the base class is executed. Thus, dynamic memory that is managed by the derived class could leak. This can be avoided by adding a virtual destructor to the base class.

## Further Reading

* [Common Weakness Enumeration (CWE) - 404](https://cwe.mitre.org/data/definitions/404.html)