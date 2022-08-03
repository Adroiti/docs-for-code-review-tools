Pattern: Throwing new instance of same exception

Issue: -

## Description

Exceptions should not be wrapped inside the same exception type and then rethrown. Prefer wrapping exceptions in more meaningful exception types.

Example of **incorrect** code:

```kotlin
fun foo() {
    try {
        // ...
    } catch (e: IllegalStateException) {
        throw IllegalStateException(e) // rethrows the same exception
    }
}
```

Example of **correct** code:

```kotlin
fun foo() {
    try {
        // ...
    } catch (e: IllegalStateException) {
        throw MyException(e)
    }
}
```

## Further Reading

* [Detekt - ThrowingNewInstanceOfSameException](https://detekt.dev/docs/rules/exceptions/#throwingnewinstanceofsameexception)