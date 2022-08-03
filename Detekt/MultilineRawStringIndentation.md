Pattern: Inconsistent multiline raw string indentation

Issue: -

## Description

This rule ensures that raw strings have a consistent indentation.

The content of a multi line raw string should have the same indentation as the enclosing expression plus the
configured indentSize. The closing triple-quotes (`"""`)  must have the same indentation as the enclosing expression.

Example of **incorrect** code:

```kotlin
val a = """
Hello World!
How are you?
""".trimMargin()

val a = """
        Hello World!
        How are you?
        """.trimMargin()
```

Example of **correct** code:

```kotlin
val a = """
    Hello World!
    How are you?
""".trimMargin()

val a = """
    Hello World!
      How are you?
""".trimMargin()
```

## Further Reading

* [Detekt - MultilineRawStringIndentation](https://detekt.dev/docs/rules/style/#multilinerawstringindentation)