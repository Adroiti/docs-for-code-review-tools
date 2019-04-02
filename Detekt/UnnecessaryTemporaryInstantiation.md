Pattern: Unnecessary temporary instantiation

Issue: -

## Description

Avoid temporary objects when converting primitive types to `String`. This has a performance penalty when compared to using primitive types directly. To solve this issue, remove the wrapping type.

Example of **incorrect** code:

```kotlin
val i = Integer(1).toString() // temporary Integer instantiation just for the conversion
```

Example of **correct** code:

```kotlin
val i = Integer.toString(1)
```

## Further Reading

* [Detekt - UnnecessaryTemporaryInstantiation](https://arturbosch.github.io/detekt/performance.html#unnecessarytemporaryinstantiation)