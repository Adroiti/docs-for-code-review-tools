Pattern: Abstract class with `public` constructor

Issue: -

## Description

Checks for `abstract` classes that define a `public` constructor, which is useless and confusing.

The following code produces a violation:

``` groovy
abstract class SomeClass {
    SomeClass() { }
}
```

## Further Reading

* [CodeNarc - AbstractClassWithPublicConstructor](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#abstractclasswithpublicconstructor-rule)