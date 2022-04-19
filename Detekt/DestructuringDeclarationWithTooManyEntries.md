Pattern: Too many entries for destructuring declaration

Issue: -

## Description

Destructuring declarations with too many entries are hard to read and understand.
To increase readability they should be refactored to reduce the number of entries or avoid using a destructuring declaration.

Example of **incorrect** code:

```kotlin
data class TooManyElements(val a: Int, val b: Int, val c: Int, val d: Int)
val (a, b, c, d) = TooManyElements(1, 2, 3, 4)
```
Example of **correct** code:

```kotlin
data class FewerElements(val a: Int, val b: Int, val c: Int)
val (a, b, c) = TooManyElements(1, 2, 3)
```

## Further Reading

* [Detekt - DestructuringDeclarationWithTooManyEntries](https://detekt.dev/style.html#destructuringdeclarationwithtoomanyentries)