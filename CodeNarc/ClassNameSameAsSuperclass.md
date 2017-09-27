Pattern: Class name same as superclass

Issue: -

## Description

Checks for any class that has an identical name to its superclass, other than the package. This can be very confusing.

Example of violations:

``` groovy
class MyClass extends other.MyClass         // violation
```

## Further Reading

* [CodeNarc - ClassNameSameAsSuperclass](http://codenarc.sourceforge.net/codenarc-rules-naming.html#ClassNameSameAsSuperclass)