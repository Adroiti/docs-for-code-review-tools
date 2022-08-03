Pattern: Untrimmed multi-line raw string

Issue: -

## Description

All the Raw strings that have more than one line should be followed by `trimMargin()` or `trimIndent()`.

Example of **incorrect** code:

```kotlin
"""
  Hello World!
  How are you?
"""
```

Example of **correct** code:

```kotlin
"""
  |  Hello World!
  |  How are you?
""".trimMargin()

"""
  Hello World!
  How are you?
""".trimIndent()

"""Hello World! How are you?"""
```

## Further Reading

* [Detekt - TrimMultilineRawString](https://detekt.dev/style.html#trimmultilinerawstring)