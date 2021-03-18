Pattern: Use of type check for exception

Issue: -

## Description

Instead of catching generic exception types and then checking for specific exception types the code should use multiple catch blocks. These catch blocks should then catch the specific exceptions.

Example of **incorrect** code:

```kotlin
fun foo() {
    try {
        // ... do some I/O
    } catch(e: IOException) {
        if (e is MyException || (e as MyException) != null) { }
    }
}
```

Example of **correct** code:

```kotlin
fun foo() {
    try {
        // ... do some I/O
    } catch(e: MyException) {
    } catch(e: IOException) {
    }

```

## Further Reading

* [Detekt - InstanceOfCheckForException](https://detekt.github.io/detekt/exceptions.html#instanceofcheckforexception)