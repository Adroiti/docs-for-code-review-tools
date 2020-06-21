Pattern: Missing override for `equals()` or `hashCode()`

Issue: -

## Description

Checks that if either the `boolean equals(Object)` or the `int hashCode()` methods are overridden within a class, then both must be overridden.

Here is an example of code that produces a violation:

``` groovy
class SomeClass {
    boolean equals(Object object) {
        // do something
    }
}
```

And so does this:

``` groovy
class SomeClass {
    int hashCode() {
        return 0
    }
}
```

## Further Reading

* [CodeNarc - EqualsAndHashCode](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#equalsandhashcode-rule)