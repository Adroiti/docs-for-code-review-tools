Pattern: Dynamic parameter return type

Issue: -

## Description

Checks that method parameters are not dynamically typed, that is they are explicitly stated and different than `def`.

Example of violations:

``` groovy
void methodWithDynamicParameter(def parameter) {              // violation
}

void methodWithParameterWithoutTypeDeclaration(parameter) {   // violation
}

void methodWithObjectParameter(Object parameter)              // OK
```

## Further Reading

* [CodeNarc - MethodParameterTypeRequired](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#methodparametertyperequired-rule)