Pattern: Use of `var` instead of `val`

Issue: -

## Description

Reports `var` declarations (locally-scoped variables) that could be `val`, as they are not re-assigned. `val` declarations are assign-once (read-only), which makes understanding the current state easier.

Example of **incorrect** code:

```kotlin
fun example() {
    var i = 1 // violation: this variable is never re-assigned
    val j = i + 1
}
```

Example of **correct** code:

```kotlin
fun example() {
    val i = 1
    val j = i + 1
}
```

## Further Reading

* [Detekt - VarCouldBeVal](https://arturbosch.github.io/detekt/style.html#varcouldbeval)