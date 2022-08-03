Pattern: Missing use of sequence

Issue: -

## Description

Long chains of collection operations will have a performance penalty due to a new list being created for each call. Consider using sequences instead.

Example of **incorrect** code:

```kotlin
listOf(1, 2, 3, 4).map { it*2 }.filter { it < 4 }.map { it*it }
```

Example of **correct** code:

```kotlin
listOf(1, 2, 3, 4).asSequence().map { it*2 }.filter { it < 4 }.map { it*it }.toList()

listOf(1, 2, 3, 4).map { it*2 }
```

## Further Reading

* [Detekt - CouldBeSequence](https://detekt.dev/docs/rules/performance/#couldbesequence)