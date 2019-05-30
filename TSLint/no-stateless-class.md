Pattern: Stateless class

Issue: -

## Description

Deprecated - This rule can be replaced with TSLint's `no-unnecessary-class`. 

A stateless class represents a failure in the
object oriented design of the system. A class without state is better
modeled as a module or given some state. A stateless class is defined as
a class with only static members and no parent class.

## Further Reading

* [TSLint - no-stateless-class](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)