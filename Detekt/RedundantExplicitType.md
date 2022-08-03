Pattern: Redundant explicit type

Issue: -

## Description

Local properties do not need their type to be explicitly provided when the inferred type matches the explicit type.

Example of **incorrect** code:

```kotlin
fun function() {
val x: String = "string"
}
```

Example of **correct** code:

```kotlin
fun function() {
val x = "string"
}
```

## Further Reading

* [Detekt - RedundantExplicitType](https://detekt.dev/docs/rules/style/#redundantexplicittype)