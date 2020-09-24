Pattern: Use of `arrayOf(...)` syntax

Issue: -

## Description

This rule detects annotations which use the `arrayOf(...)` syntax instead of the array literal `[...]` syntax. The latter should be preferred as it is more readable.
Example of **incorrect** code:

```kotlin
Example of **correct** code:

```kotlin

## Further Reading

* [Detekt - UseArrayLiteralsInAnnotations](https://arturbosch.github.io/detekt/style.html#usearrayliteralsinannotations)