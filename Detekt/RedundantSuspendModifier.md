Pattern: Redundant `suspend` modifier

Issue: -

## Description

`suspend` modifier should only be used where needed, otherwise the function can only be used from other suspending functions. This needlessly restricts use of the function and should be avoided by removing the `suspend` modifier where it's not needed.

Example of **incorrect** code:

```kotlin
Example of **correct** code:

```kotlin

## Further Reading

* [Detekt - RedundantSuspendModifier](https://arturbosch.github.io/detekt/coroutines.html#redundantsuspendmodifier)