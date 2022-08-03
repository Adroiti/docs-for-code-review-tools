Pattern: Use of `isEmpty`/`isBlank`

Issue: -

## Description

This rule detects `isEmpty` or `isBlank` calls to assign a default value. They can be replaced with `ifEmpty` or `ifBlank` calls.

Example of **incorrect** code:

```kotlin
fun test(list: List<Int>, s: String) {
    val a = if (list.isEmpty()) listOf(1) else list
    val b = if (list.isNotEmpty()) list else listOf(2)
    val c = if (s.isBlank()) "foo" else s
    val d = if (s.isNotBlank()) s else "bar"
}
```

Example of **correct** code:

```kotlin
fun test(list: List<Int>, s: String) {
    val a = list.ifEmpty { listOf(1) }
    val b = list.ifEmpty { listOf(2) }
    val c = s.ifBlank { "foo" }
    val d = s.ifBlank { "bar" }
}
```

## Further Reading

* [Detekt - UseIfEmptyOrIfBlank](https://detekt.dev/docs/rules/style/#useifemptyorifblank)