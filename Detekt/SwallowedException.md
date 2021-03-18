Pattern: Lost exception

Issue: -

## Description

Exceptions should not be swallowed. This rule reports all instances where exceptions are `caught` and not correctly passed into a newly thrown exception.

Example of **incorrect** code:

```kotlin
fun foo() {
    try {
        // ...
    } catch(e: IOException) {
        throw MyException(e.message) // e is swallowed
    }
    try {
        // ...
    } catch(e: IOException) {
        throw MyException() // e is swallowed
    }
    try {
        // ...
    } catch(e: IOException) {
        bar() // exception is unused
    }
}
```

Example of **correct** code:

```kotlin
fun foo() {
    try {
        // ...
    } catch(e: IOException) {
        throw MyException(e)
    }
    try {
        // ...
    } catch(e: IOException) {
        println(e) // logging is ok here
    }
}
```

## Further Reading

* [Detekt - SwallowedException](https://detekt.github.io/detekt/exceptions.html#swallowedexception)