Pattern: Missing newline

Issue: -

## Description

Checks for missing newlines (for example between parentheses of a multi-line function call).

Example of **incorrect** code:

```kotlin
val x = f(
    a,
    b,
    c)
```

Example of **correct** code:

```kotlin
val x = f(
    a,
    b,
    c
)
```

## Further Reading

* [Detekt - Wrapping](https://detekt.dev/docs/rules/formatting/#wrapping)