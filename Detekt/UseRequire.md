Pattern: Missing use of `require`

Issue: -

## Description

Kotlin provides a much more concise way to check preconditions than to manually throw an `IllegalArgumentException`.

Example of **incorrect** code:

```kotlin
if (value == null) throw new IllegalArgumentException("value should not be null")
if (value < 0) throw new IllegalArgumentException("value is $value but should be at least 0")
```

Example of **correct** code:

```kotlin
requireNotNull(value) {"value should not be null"}
require(value >= 0) { "value is $value but should be at least 0" }
```

## Further Reading

* [Detekt - UseRequire](https://detekt.github.io/detekt/style.html#userequire)