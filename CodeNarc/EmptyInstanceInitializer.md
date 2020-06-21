Pattern: Empty instance initializer

Issue: -

## Description

An empty class instance initializer was found. It is safe to remove it. Example:

``` groovy
class SomeClass {
    { }     // empty instance initializer, not a closure
}
```

## Further Reading

* [CodeNarc - EmptyInstanceInitializer](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#emptyinstanceinitializer-rule)