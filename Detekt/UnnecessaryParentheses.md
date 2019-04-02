Pattern: Unnecessary parentheses around expression

Issue: -

## Description

This rule reports unnecessary parentheses around expressions. These unnecessary parentheses can safely be removed.

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