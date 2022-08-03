Pattern: Complex condition

Issue: -

## Description

Complex conditions make it hard to understand which cases lead to the condition being `true` or `false`. To improve
readability and understanding of complex conditions consider extracting them into well-named functions or variables
and call those instead.

Example of **incorrect** code:

```kotlin
val str = "foo"
val isFoo = if (str.startsWith("foo") && !str.endsWith("foo") && !str.endsWith("bar") && !str.endsWith("_")) {
    // ...
}
```

Example of **correct** code:

```kotlin
val str = "foo"
val isFoo = if (str.startsWith("foo") && hasCorrectEnding()) {
    // ...
}

fun hasCorrectEnding() = return !str.endsWith("foo") && !str.endsWith("bar") && !str.endsWith("_")
```

## Further Reading

* [Detekt - ComplexCondition](https://detekt.dev/docs/rules/complexity/#complexcondition)