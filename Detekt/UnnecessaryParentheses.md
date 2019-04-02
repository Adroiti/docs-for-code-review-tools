Pattern: Unnecessary `()` around expression

Issue: -

## Description

Unnecessary parentheses can be safely removed.

Example of **incorrect** code:

```kotlin
val local = (5 + 3)

if ((local == 8)) { }

fun foo() {
    function({ input -> println(input) })
}
```

Example of **correct** code:

```kotlin
val local = 5 + 3

if (local == 8) { }

fun foo() {
    function { input -> println(input) }
}
```

## Further Reading

* [Detekt - UnnecessaryParentheses](https://arturbosch.github.io/detekt/style.html#unnecessaryparentheses)