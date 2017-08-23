Pattern: Use initialization list

Issue: -

## Description

When an object of a class is created, the constructors of all member variables are called consecutively in the order the variables are declared, even if you don`t explicitly write them to the initialization list. You could avoid assigning `variable` a value by passing the value to the constructor in the initialization list.

## Further Reading

* [Common Weakness Enumeration (CWE) - 398](https://cwe.mitre.org/data/definitions/398.html)