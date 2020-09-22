Pattern: Use of non-boolean property with `is` prefix

Issue: -

## Description

Reports when property with `is` prefix doesn't have a boolean type.

Example of **incorrect** code:

```kotlin
val isEnabled: Int = 500
```

Example of **correct** code:

```kotlin
val isEnabled: Boolean = false
```

## Further Reading

* [Detekt - NonBooleanPropertyPrefixedWithIs](https://detekt.github.io/detekt/naming.html#nonbooleanpropertyprefixedwithis)