Pattern: Interface with same name as super-interface

Issue: -

## Description

Checks for any interface that has an identical name to its super-interface, other than the package. This can be very confusing.

Example of violations:

``` groovy
interface SomeInterface extends other.SomeInterface { }     // violation
```

## Further Reading

* [CodeNarc - InterfaceNameSameAsSuperInterface](https://codenarc.github.io/CodeNarc/codenarc-rules-naming.html#interfacenamesameassuperinterface-rule)