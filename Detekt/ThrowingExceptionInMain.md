Pattern: Throwing exception in `main`

Issue: -

## Description

This rule reports all exceptions that are thrown in a `main` method. An exception should only be thrown if it can be handled by a "higher" function.

Example of **incorrect** code:

```kotlin
fun main(args: Array<String>) {
    // ...
    throw IOException() // exception should not be thrown here
}
```

## Further Reading

* [Detekt - ThrowingExceptionInMain](https://arturbosch.github.io/detekt/exceptions.html#throwingexceptioninmain)