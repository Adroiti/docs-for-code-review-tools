Pattern: Missing use of empty counterpart

Issue: -

## Description

Instantiation of an object's "empty" state should use the object's "empty" initializer for clarity purposes.

Example of **incorrect** code:

```kotlin
arrayOf()
listOf() // or listOfNotNull()
mapOf()
sequenceOf()
setOf()
```

Example of **correct** code:

```kotlin
emptyArray()
emptyList()
emptyMap()
emptySequence()
emptySet()
```

## Further Reading

* [Detekt - UseEmptyCounterpart](https://detekt.dev/docs/rules/style/#useemptycounterpart)