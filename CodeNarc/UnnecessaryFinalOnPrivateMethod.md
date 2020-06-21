Pattern: Unnecessary `final` on private method

Issue: -

## Description

A private method is marked `final`. Private methods cannot be overridden, so marking it `final` is unnecessary.

Example of violations:

``` groovy
private final method() {}
```

## Further Reading

* [CodeNarc - UnnecessaryFinalOnPrivateMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessaryfinalonprivatemethod-rule)