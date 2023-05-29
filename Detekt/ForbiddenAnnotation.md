Pattern: Forbidden annotation

Issue: -

## Description

This rule allows to set a list of forbidden annotations. This can be used to discourage the use
of language annotations which do not require explicit import.

Example of **incorrect** code:

```kotlin
@@SuppressWarnings("unused")
class SomeClass()
```

Example of **correct** code:

```kotlin
@@Suppress("unused")
class SomeClass()
```

## Further Reading

* [Detekt - ForbiddenAnnotation](https://detekt.dev/style.html#forbiddenannotation)