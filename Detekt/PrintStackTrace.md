Pattern: Printing stacktrace of an exception

Issue: -

## Description

Instead of simply printing a stacktrace a better logging solution should be used.

Example of **incorrect** code:

```kotlin
fun foo() {
    Thread.dumpStack()
}

fun bar() {
    try {
        // ...
    } catch (e: IOException) {
        e.printStackTrace()
    }
}
```

Example of **correct** code:

```kotlin
val LOGGER = Logger.getLogger()

fun bar() {
    try {
        // ...
    } catch (e: IOException) {
        LOGGER.info(e)
    }
}
```

## Further Reading

* [Detekt - PrintStackTrace](https://detekt.github.io/detekt/exceptions.html#printstacktrace)