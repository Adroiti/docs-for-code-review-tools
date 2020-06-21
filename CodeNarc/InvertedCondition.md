Pattern: Use of inverted condition

Issue: -

## Description

An inverted condition is one where a constant expression is used on the left hand side of the equals comparison. Such conditions can be confusing especially when used in assertions where the expected value is by convention placed on the right hand side of the comparison.

Example of violations:

``` groovy
boolean isTenCharactersLong(String value) {
    10 == value.size()  // violation
}
```

## Further Reading

* [CodeNarc - InvertedCondition](https://codenarc.github.io/CodeNarc/codenarc-rules-convention.html#invertedcondition-rule)