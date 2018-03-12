Pattern: Missing `@Override` annotation

Issue: -

## Description

Checks for methods that override a method in a superclass or implement a method in an interface but are not annotated with `@Override`.

Consistent use of `@Override` annotation helps in spotting situations when the intent was to override a method but because of a mistake in method signature that is not the case. Additionally, applying `@Override` annotation to all overridden methods helps in spotting unnecessary methods which no longer override any methods after removing them from superclasses or implemented interfaces because such annotated methods will cause compilation errors.

Example of violation:

``` groovy
class ClassOverridingToString {
    String toString() {
      "ClassOverridingToString"
    }
}
```

## Further Reading

* [CodeNarc - MissingOverrideAnnotation](http://codenarc.sourceforge.net/codenarc-rules-enhanced.html#MissingOverrideAnnotation)