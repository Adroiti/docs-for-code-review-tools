Pattern: Unnecessary braces in `when`

Issue: -

## Description

This rule reports unnecessary braces in when expressions. These optional braces should be removed.

Example of **incorrect** code:

```kotlin
val i = 1
when (i) {
    1 -> { println("one") } // unnecessary curly braces since there is only one statement
    else -> println("else")
}
```

Example of **correct** code:

```kotlin
val i = 1
when (i) {
    1 -> println("one")
    else -> println("else")
}
```

## Further Reading

* [Detekt - OptionalWhenBraces](https://arturbosch.github.io/detekt/style.html#optionalwhenbraces)