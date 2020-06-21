Pattern: `Cloneable` without `clone()`

Issue: -

## Description

Checks for classes that implement the `java.lang.Cloneable` interface without implementing the `clone()` method.

Here is an example of code that produces a violation:

``` groovy
class BadClass implements Cloneable {
    def someMethod()
}
```

## Further Reading

* [CodeNarc - CloneableWithoutClone](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#cloneablewithoutclone-rule)