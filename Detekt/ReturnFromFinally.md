Pattern: Use of `return` from `finally`

Issue: -

## Description

Reports all `return` statements in `finally` blocks. Using `return` statements in `finally` blocks can discard and hide exceptions that are thrown in the `try` block.

Example of **incorrect** code:

```kotlin
fun foo() {
    try {
        throw MyException()
    } finally {
        return // prevents MyException from being propagated
    }
}
```

## Further Reading

* [Detekt - ReturnFromFinally](https://arturbosch.github.io/detekt/exceptions.html#returnfromfinally)