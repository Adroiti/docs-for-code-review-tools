Pattern: Exception without message or cause

Issue: -

## Description

Exceptions should always call one of the constructor overloads to provide a message or a cause. Exceptions should be meaningful and contain as much detail about the error case as possible. This will help to track down an underlying issue in a better way.

Example of **incorrect** code:

```kotlin
fun foo(bar: Int) {
    if (bar < 1) {
        throw IllegalArgumentException()
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

* [Detekt - ThrowingExceptionsWithoutMessageOrCause](https://detekt.dev/docs/rules/exceptions/#throwingexceptionswithoutmessageorcause)