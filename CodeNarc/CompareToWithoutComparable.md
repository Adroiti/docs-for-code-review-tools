Pattern: `compareTo()` without `Comparable`

Issue: -

## Description

If you implement a `compareTo()` method then you should also implement the `Comparable` interface. If you don't then you could possibly get an exception if the Groovy `==` operator is invoked on your object. This is an issue fixed in Groovy 1.8 but present in previous versions.

Here is an example of code that produces a violation:

``` groovy
class BadClass {
    int compareTo(Object o) { ... }
}
```

Known limitations:

-   This rule is not able to determine if the class extends a superclass that itself implements `Comparable`, or if it implements an interface that extends `Comparable`. In those cases, this rule produces a false violation.

## Further Reading

* [CodeNarc - CompareToWithoutComparable](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#comparetowithoutcomparable-rule)