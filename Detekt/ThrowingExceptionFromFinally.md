Pattern: Throwing exception from `finally`

Issue: -

## Description

This rule reports all cases where exceptions are thrown from a `finally` block. Throwing exceptions from a `finally` block should be avoided as it can lead to confusion and discarded exceptions.

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

* [Detekt - ThrowingExceptionFromFinally](https://arturbosch.github.io/detekt/exceptions.html#throwingexceptionfromfinally)