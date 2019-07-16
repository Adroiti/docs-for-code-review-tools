Pattern: Missing use of `check()`/`error()`

Issue: -

## Description

Kotlin provides a much more concise way to check invariants as well as _pre-_ and _post_ conditions than to manually throw an `IllegalStateException`.

Example of **incorrect** code:

```kotlin
if (value == null) throw new IllegalStateException("value should not be null")
if (value < 0) throw new IllegalStateException("value is $value but should be at least 0")
when(a) {
  1 -> doSomething()
  else -> throw IllegalStateException("Unexpected value")
}
```

Example of **correct** code:

```kotlin
checkNotNull(value) {"value should not be null"}
check(value >= 0) { "value is $value but should be at least 0" }
when(a) {
  1 -> doSomething()
  else -> error("Unexpected value")
}
```

## Further Reading

* [Detekt - UseCheckOrError](https://arturbosch.github.io/detekt/style.html#usecheckorerror)