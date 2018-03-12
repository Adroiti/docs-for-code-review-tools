Pattern: Missing explicit variable type

Issue: -

## Description

Checks that variable types are explicitly specified in declarations (and not using `def`).

Example of violations:

``` groovy
class MyClass {
    void doStuff() {
        final NAME = "joe"          // violation
        def count = 0, max = 99     // violation
        def defaultName             // violation
    }
}
```

## Further Reading

* [CodeNarc - VariableTypeRequired](http://codenarc.sourceforge.net/codenarc-rules-convention.html#VariableTypeRequired)