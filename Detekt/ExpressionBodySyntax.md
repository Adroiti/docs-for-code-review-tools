Pattern: Use of verbose function body

Issue: -

## Description

Functions which only contain a `return` statement can be collapsed to an expression body. This shortens and cleans up the code.

Example of **incorrect** code:

```kotlin
fun stuff(): Int {
    return 5
}
```

Example of **correct** code:

```kotlin
fun stuff() = 5

fun stuff() {
    return
        moreStuff()
            .getStuff()
            .stuffStuff()
}
```

## Further Reading

* [Detekt - ExpressionBodySyntax](https://detekt.github.io/detekt/style.html#expressionbodysyntax)