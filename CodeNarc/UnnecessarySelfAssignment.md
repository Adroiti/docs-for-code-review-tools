Pattern: Unnecessary self assignment

Issue: -

## Description

Method contains a pointless self-assignment to a variable or property. Either the code is pointless or the `equals()`/`get()` method has been overridden to have a side effect.

Examples:

``` groovy
x = x               // violation
def method(y) {
    y = y           // violation
}
a.b.c = a.b.c       // violation

x = y               // acceptable
a.b = a.zz          // acceptable
a.b = a().b         // acceptable
```

## Further Reading

* [CodeNarc - UnnecessarySelfAssignment](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessarySelfAssignment)