Pattern: Empty instance initializer

Issue: -

## Description

An empty class instance initializer was found. It is safe to remove it. Example:

``` groovy
class MyClass {
    { }     // empty instance initializer, not a closure
}
```

## Further Reading

* [CodeNarc - EmptyInstanceInitializer](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptyInstanceInitializer)