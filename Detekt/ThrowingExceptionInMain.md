Pattern: Throwing exception in `main`

Issue: -

## Description

An exception should only be thrown if it can be handled by a "higher" function.

Example of **incorrect** code:

```kotlin
fun main(args: Array<String>) {
    // ...
    throw IOException() // exception should not be thrown here
}
```

## Further Reading

* [Detekt - ThrowingExceptionInMain](https://detekt.github.io/detekt/exceptions.html#throwingexceptioninmain)