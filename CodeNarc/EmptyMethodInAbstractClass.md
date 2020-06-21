Pattern: Empty method in abstract class

Issue: -

## Description

An empty method in an abstract class should be abstract instead, as developer may rely on this empty implementation rather than code the appropriate one.

``` groovy
abstract class SomeClass {
    def couldBeAbstract_1() {
        return null  // Should be abstract method
    }

    void couldBeAbstract_2() {
        // Should be abstract method
    }
}
```

## Further Reading

* [CodeNarc - EmptyMethodInAbstractClass](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#emptymethodinabstractclass-rule)