Pattern: Unnecessary braces in `when`

Issue: -

## Description

These optional `when` braces should be removed.

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

* [Detekt - OptionalWhenBraces](https://detekt.dev/docs/rules/style/#optionalwhenbraces)