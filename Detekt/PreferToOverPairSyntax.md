Pattern: Use of `Pair` constructor

Issue: -

## Description

Detects the usage of the `Pair` constructor to create pairs of values. Use the `to` syntax instead.

Example of **incorrect** code:

```kotlin
val pair = Pair(1, 2)
```

Example of **correct** code:

```kotlin
val pair = 1 to 2
```

## Further Reading

* [Detekt - PreferToOverPairSyntax](https://detekt.github.io/detekt/style.html#prefertooverpairsyntax)