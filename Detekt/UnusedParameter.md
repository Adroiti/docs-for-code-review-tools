Pattern: Unused parameter

Issue: -

## Description

An unused parameter can be removed to simplify the signature of the function.

Example of **incorrect** code:

```kotlin
fun foo(unused: String) {
  println()
}
```

Example of **correct** code:

```kotlin
fun foo(used: String) {
  println(used)
}
```

## Further Reading

* [Detekt - UnusedParameter](https://detekt.dev/style.html#unusedparameter)