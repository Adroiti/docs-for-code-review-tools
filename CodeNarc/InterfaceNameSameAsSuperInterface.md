Pattern: Interface with same name as super-interface

Issue: -

## Description

Checks for any interface that has an identical name to its super-interface, other than the package. This can be very confusing.

Example of violations:

``` groovy
interface MyInterface extends other.MyInterface { }     // violation
```

## Further Reading

* [CodeNarc - InterfaceNameSameAsSuperInterface](http://codenarc.sourceforge.net/codenarc-rules-naming.html#InterfaceNameSameAsSuperInterface)