Pattern: Redundant `suspend` modifier

Issue: -

## Description

`suspend` modifier should only be used where needed, otherwise the function can only be used from other suspending functions. This needlessly restricts use of the function and should be avoided by removing the `suspend` modifier where it's not needed.

Example of **incorrect** code:

```kotlinsuspend fun normalFunction() {  println("string")}```
Example of **correct** code:

```kotlinfun normalFunction() {  println("string")}```

## Further Reading

* [Detekt - RedundantSuspendModifier](https://detekt.dev/docs/rules/coroutines/#redundantsuspendmodifier)