Pattern: Uncollapsed `if` statement

Issue: -

## Description

Reported `if` statement can be collapsed - this can reduce nesting and help improve readability. However it should be carefully considered if merging the if statements actually does improve readability or if it hides some edge-cases from the reader.

Example of **incorrect** code:

```kotlin
val i = 1
if (i > 0) {
    if (i < 5) {
        println(i)
    }
}
```

Example of **correct** code:

```kotlin
val i = 1
if (i > 0 && i < 5) {
    println(i)
}
```

## Further Reading

* [Detekt - CollapsibleIfStatements](https://arturbosch.github.io/detekt/style.html#collapsibleifstatements)