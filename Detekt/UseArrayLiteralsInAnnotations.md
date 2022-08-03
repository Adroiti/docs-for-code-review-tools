Pattern: Use of `arrayOf(...)` syntax

Issue: -

## Description

This rule detects annotations which use the `arrayOf(...)` syntax instead of the array literal `[...]` syntax. The latter should be preferred as it is more readable.
Example of **incorrect** code:

```kotlin@@PositiveCase(arrayOf("..."))```
Example of **correct** code:

```kotlin@@NegativeCase(["..."])```

## Further Reading

* [Detekt - UseArrayLiteralsInAnnotations](https://detekt.dev/docs/rules/style/#usearrayliteralsinannotations)