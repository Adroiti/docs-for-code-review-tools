Pattern: Class name same as superclass

Issue: -

## Description

Checks for any class that has an identical name to its superclass, other than the package. This can be very confusing.

Example of violations:

``` groovy
class SomeClass extends other.SomeClass         // violation
```

## Further Reading

* [CodeNarc - ClassNameSameAsSuperclass](https://codenarc.github.io/CodeNarc/codenarc-rules-naming.html#classnamesameassuperclass-rule)