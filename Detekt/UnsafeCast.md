Pattern: Use of unsafe cast

Issue: -

## Description

Reports casts which are unsafe. In case the cast is not possible it will throw an exception.

Example of **incorrect** code:

```kotlin
fun foo(s: Any) {
    println(s as Int)
}
```

Example of **correct** code:

```kotlin
fun foo(s: Any) {
    println((s as? Int) ?: 0)
}
```

## Further Reading

* [Detekt - UnsafeCast](https://arturbosch.github.io/detekt/potential-bugs.html#unsafecast)