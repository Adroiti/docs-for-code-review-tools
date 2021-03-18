Pattern: Too many `throw` statements

Issue: -

## Description

Functions should have clear `throw` statements. Functions with many `throw` statements can be harder to read and lead to confusion. Instead prefer to limit the amount of `throw` statements in a function.

Example of **incorrect** code:

```kotlin
fun foo(i: Int) {
    when (i) {
        1 -> throw IllegalArgumentException()
        2 -> throw IllegalArgumentException()
        3 -> throw IllegalArgumentException()
    }
}
```

Example of **correct** code:

```kotlin
fun foo(i: Int) {
    when (i) {
        1,2,3 -> throw IllegalArgumentException()
    }
}
```

## Further Reading

* [Detekt - ThrowsCount](https://detekt.github.io/detekt/style.html#throwscount)