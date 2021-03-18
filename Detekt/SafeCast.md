Pattern: Missing use of safe cast

Issue: -

## Description

Found cast could be replaced with safe casts instead.

Example of **incorrect** code:

```kotlin
fun numberMagic(number: Number) {
    val i = if (number is Int) number else null
    // ...
}
```

Example of **correct** code:

```kotlin
fun numberMagic(number: Number) {
    val i = number as? Int
    // ...
}
```

## Further Reading

* [Detekt - SafeCast](https://detekt.github.io/detekt/style.html#safecast)