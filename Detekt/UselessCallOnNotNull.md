Pattern: Redundant call on not null

Issue: -

## Description

The Kotlin `stdlib` provides some functions that are designed to operate on references that may be null. These
functions can also be called on non-nullable references or on collections or sequences that are known to be empty -
the calls are redundant in this case and can be removed or should be changed to a call that does not check whether
the value is null or not.

Example of **incorrect** code:

```kotlin
val testList = listOf("string").orEmpty()
val testList2 = listOf("string").orEmpty().map { _ }
val testString = ""?.isNullOrBlank()
```

Example of **correct** code:

```kotlin
val testList = listOf("string")
val testList2 = listOf("string").map { }
val testString = ""?.isBlank()
```

## Further Reading

* [Detekt - UselessCallOnNotNull](https://detekt.github.io/detekt/style.html#uselesscallonnotnull)