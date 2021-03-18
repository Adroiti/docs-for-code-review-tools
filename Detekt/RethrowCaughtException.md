Pattern: Rethrown exception without modification

Issue: -

## Description

Reports all exceptions that are caught and then later re-thrown without modification. It ignores caught exceptions that are rethrown if there is work done before that.

Example of **incorrect** code:

```kotlin
fun foo() {
    try {
        // ...
    } catch (e: IOException) {
        throw e
    }
}
```

Example of **correct** code:

```kotlin
fun foo() {
    try {
        // ...
    } catch (e: IOException) {
        throw MyException(e)
    }
    try {
        // ...
    } catch (e: IOException) {
        print(e)
        throw e
    }
    try {
        // ...
    } catch (e: IOException) {
        print(e.message)
        throw e
    }
}
```

## Further Reading

* [Detekt - RethrowCaughtException](https://detekt.github.io/detekt/exceptions.html#rethrowcaughtexception)