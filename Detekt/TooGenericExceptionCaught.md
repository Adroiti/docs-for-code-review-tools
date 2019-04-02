Pattern: Too generic caught exception

Issue: -

## Description

This rule reports `catch` blocks for exceptions that have a type that is too generic. It should be preferred to catch specific exceptions to the case that is currently handled. If the scope of the caught exception is too broad it can lead to unintended exceptions being caught.

Example of **incorrect** code:

```kotlin
fun foo() {
    try {
        // ... do some I/O
    } catch(e: Exception) { } // too generic exception caught here
}
```

Example of **correct** code:

```kotlin
fun foo() {
    try {
        // ... do some I/O
    } catch(e: IOException) { }
}
```

## Further Reading

* [Detekt - TooGenericExceptionCaught](https://arturbosch.github.io/detekt/exceptions.html#toogenericexceptioncaught)