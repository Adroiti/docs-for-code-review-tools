Pattern: Unnecessary super type

Issue: -

## Description

Inheriting from `Any` or `Object` is unnecessary and should simply be removed.

Example of **incorrect** code:

```kotlin
class A : Any()
class B : Object()
```

## Further Reading

* [Detekt - UnnecessaryInheritance](https://detekt.github.io/detekt/style.html#unnecessaryinheritance)