Pattern: Use of forbidden `Void`

Issue: -

## Description

This rule detects usages of `Void` and reports them as forbidden. The Kotlin type `Unit` should be used instead. This type corresponds to the `Void` class in Java and has only one value - the `Unit` object.

Example of **incorrect** code:

```kotlin
runnable: () -> Void
var aVoid: Void? = null
```

Example of **correct** code:

```kotlin
runnable: () -> Unit
Void::class
```

## Further Reading

* [Detekt - ForbiddenVoid](https://arturbosch.github.io/detekt/style.html#forbiddenvoid)