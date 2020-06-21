Pattern: `clone()` without `Cloneable`

Issue: -

## Description

The method `clone()` should only be declared if the class implements the `Cloneable` interface.

Example of violations:

``` groovy
class ValueClass {
    ValueClass clone() {
    }
}
```

## Further Reading

* [CodeNarc - CloneWithoutCloneable](https://codenarc.github.io/CodeNarc/codenarc-rules-enhanced.html#clonewithoutcloneable-rule)