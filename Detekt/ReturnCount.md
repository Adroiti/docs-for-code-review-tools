Pattern: Too many returns in method

Issue: -

## Description

Restrict the number of return methods allowed in methods.

Having many exit points in a function can be confusing and impacts readability of the code.

Example of **incorrect** code:

```kotlin
fun foo(i: Int): String {
    when (i) {
        1 -> return "one"
        2 -> return "two"
        else -> return "other"
    }
}
```

Example of **correct** code:

```kotlin
fun foo(i: Int): String {
    return when (i) {
        1 -> "one"
        2 -> "two"
        else -> "other"
    }
}
```

## Further Reading

* [Detekt - ReturnCount](https://detekt.dev/docs/rules/style/#returncount)