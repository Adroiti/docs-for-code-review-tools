Pattern: Unreachable catch block

Issue: -

## Description

Catch blocks can be unreachable if the exception has already been caught in the block above.

Example of **incorrect** code:

```java
fun test() {
    try {
        foo()
    } catch (t: Throwable) {
        bar()
    } catch (e: Exception) {
        // Unreachable
        baz()
    }
}

```

Example of **correct** code:

```java
fun test() {
    try {
        foo()
    } catch (e: Exception) {
        baz()
    } catch (t: Throwable) {
        bar()
    }
}

```

## Further Reading

* [Detekt - UnreachableCatchBlock](https://detekt.github.io/detekt/potential-bugs.html#unreachablecatchblock)