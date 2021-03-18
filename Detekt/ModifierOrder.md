Pattern: Incorrect modifier order

Issue: -

## Description

Reports cases in the code where modifiers are not in the correct order.

Example of **incorrect** code:

```kotlin
lateinit internal private val str: String
```

Example of **correct** code:

```kotlin
private internal lateinit val str: String
```

## Further Reading

* [Detekt - ModifierOrder](https://detekt.github.io/detekt/style.html#modifierorder)