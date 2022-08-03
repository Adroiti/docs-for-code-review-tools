Pattern: Missing braces for multi-line statement

Issue: -

## Description

Adding braces would improve readability and avoid possible errors.

Example of **incorrect** code:

```kotlin
val i = 1
if (i > 0)
    println(i)
```

Example of **correct** code:

```kotlin
val x = if (condition) 5 else 4
```

## Further Reading

* [Detekt - MandatoryBracesIfStatements](https://detekt.dev/docs/rules/style/#mandatorybracesifstatements)