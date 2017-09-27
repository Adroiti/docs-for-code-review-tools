Pattern: Empty static initializer

Issue: -

## Description

Empty static initializer serves no purpose. It is safe to remove it. Example:

``` groovy
class SomeClass {
    static { }
}
```

## Further Reading

* [CodeNarc - EmptyStaticInitializer](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptyStaticInitializer)