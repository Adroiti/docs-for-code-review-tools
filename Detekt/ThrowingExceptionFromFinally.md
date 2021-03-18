Pattern: Throwing exception from `finally`

Issue: -

## Description

Throwing exceptions from a `finally` block should be avoided as it can lead to confusion and discarded exceptions.

Example of **incorrect** code:

```kotlin
fun foo() {
    try {
        // ...
    } finally {
        throw IOException()
    }
}
```

## Further Reading

* [Detekt - ThrowingExceptionFromFinally](https://detekt.github.io/detekt/exceptions.html#throwingexceptionfromfinally)