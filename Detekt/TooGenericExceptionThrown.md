Pattern: Too generic thrown exception

Issue: -

## Description

Reports thrown exceptions that have a type that is too generic. It should be preferred to throw specific exceptions to the case that has currently occurred.

Example of **incorrect** code:

```kotlin
fun foo(bar: Int) {
    if (bar < 1) {
        throw Exception() // too generic exception thrown here
    }
    // ...
}
```

Example of **correct** code:

```kotlin
fun foo(bar: Int) {
    if (bar < 1) {
        throw IllegalArgumentException("bar must be greater than zero")
    }
    // ...
}
```

## Further Reading

* [Detekt - TooGenericExceptionThrown](https://detekt.github.io/detekt/exceptions.html#toogenericexceptionthrown)