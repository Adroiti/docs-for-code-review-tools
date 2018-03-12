Pattern: Dynamic method return type

Issue: -

## Description

Checks that method return types are not dynamic, that is they are explicitly stated and different than `def`.

Example of violations:

``` groovy
def methodWithDynamicReturnType() {    // violation
}

private methodWithoutReturnType() {    // violation
}

Object objectReturningMethod() {       // OK
}
```

## Further Reading

* [CodeNarc - MethodReturnTypeRequired](http://codenarc.sourceforge.net/codenarc-rules-convention.html#MethodReturnTypeRequired)