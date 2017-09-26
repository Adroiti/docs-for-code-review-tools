Pattern: Multiple unary operators

Issue: -

## Description

Checks for multiple consecutive unary operators. These are confusing, and are likely typos and bugs.

Example of violations:

``` groovy
int z = ~~2             // violation
boolean b = !!true      // violation
boolean c = !!!false    // 2 violations
int j = -~7             // violation
int k = +~8             // violation
```

## Further Reading

* [CodeNarc - MultipleUnaryOperators](http://codenarc.sourceforge.net/codenarc-rules-basic.html#MultipleUnaryOperators)