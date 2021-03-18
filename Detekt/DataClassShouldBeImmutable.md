Pattern: Mutable property in data class

Issue: -

## Description

Data classes should mainly be used to store immutable data. This rule assumes that they should not contain any mutable properties.

Example of **incorrect** code:

```kotlin
data class MutableDataClass(var i: Int) {
    var s: String? = null
}
```

Example of **correct** code:

```kotlin
data class ImmutableDataClass(
    val i: Int,
    val s: String?
)
```

## Further Reading

* [Detekt - DataClassShouldBeImmutable](https://detekt.github.io/detekt/style.html#dataclassshouldbeimmutable)