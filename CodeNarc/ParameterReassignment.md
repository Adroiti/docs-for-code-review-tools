Pattern: Parameter reassignment

Issue: -

## Description

Checks for a method or closure parameter being reassigned to a new value within the body of the method/closure, which is a confusing and questionable practice. Use a temporary variable instead.

Example of violations:

``` groovy
void someMethod(int a, String b) {
    println a
    b = 'new value'     // violation
}

def someClosure1 = { int a, b ->
    a = 123             // violation
}
```

## Further Reading

* [CodeNarc - ParameterReassignment](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#parameterreassignment-rule)