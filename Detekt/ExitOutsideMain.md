Pattern: Exit outside `main()`

Issue: -

## Description

Flags use of `System.exit()` and Kotlin's `exitProcess()` when used outside the `main` function. This makes code more
difficult to test, causes unexpected behaviour on Android, and is a poor way to signal a failure in the program. In
almost all cases it is more appropriate to throw an exception.

Example of **incorrect** code:

```kotlin
fun randomFunction() {
    val result = doWork()
    if (result == FAILURE) {
        exitProcess(2)
    } else {
        exitProcess(0)
    }
}
```

Example of **correct** code:

```kotlin
fun main() {
    val result = doWork()
    if (result == FAILURE) {
        exitProcess(2)
    } else {
        exitProcess(0)
    }
}
```

## Further Reading

* [Detekt - ExitOutsideMain](https://detekt.dev/docs/rules/potential-bugs/#exitoutsidemain)