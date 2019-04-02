Pattern: Unnecessary super type

Issue: -

## Description

This rule reports unnecessary super types. Inheriting from `Any` or `Object` is unnecessary and should simply be removed.

Example of **incorrect** code:

```kotlin
class A : Any()
class B : Object()
```

## Further Reading

* [Detekt - UnnecessaryInheritance](https://arturbosch.github.io/detekt/style.html#unnecessaryinheritance)