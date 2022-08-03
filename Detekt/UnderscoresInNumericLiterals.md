Pattern: Missing underscore in numeric literal

Issue: -

## Description

Detects and reports decimal base `10` numeric literals above a certain length that should be underscore separated for readability. Underscores that do not make groups of `3` digits are also reported even if their length is under the `acceptableDecimalLength`. For `Serializable` classes or objects, the field `serialVersionUID` is explicitly ignored.

Example of **incorrect** code:

```kotlin
object Money {
    const val DEFAULT_AMOUNT = 1000000
}
```

Example of **correct** code:

```kotlin
object Money {
    const val DEFAULT_AMOUNT = 1_000_000
}
```

## Further Reading

* [Detekt - UnderscoresInNumericLiterals](https://detekt.dev/docs/rules/style/#underscoresinnumericliterals)