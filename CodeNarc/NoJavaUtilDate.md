Pattern: Use of `java.util.Date`

Issue: -

## Description

Do not use the `java.util.Date` class. Prefer the classes in the java.time.\* packages. This rule checks for construction of new java.util.Date objects.

If the class imports another `Date` class, then references to `new Date()` will not cause a violation.

Example of violations:

``` groovy
def timestamp = new Date()              // violation
Date myDate = new java.util.Date()      // violation
Date startTime = new Date(123456789L)   // violation
```

Known limitations:

-   Will cause an incorrect violation if the source code is referring to
a different `Date` class from the current package. In that case, it
may be better to just disable this rule (either per class or globally).

## Further Reading

* [CodeNarc - NoJavaUtilDate](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#nojavautildate-rule)