Pattern: Use of double negative lambda

Issue: -

## Description

Detects negation in lambda blocks where the function name is also in the negative (like `takeUnless`).
A double negative is harder to read than a positive. In particular, if there are multiple conditions with `&&` etc. inside the lambda, then the reader may need to unpack these using DeMorgan's laws. Consider rewriting the lambda to use a positive version of the function (like `takeIf`).

Example of **incorrect** code:

```kotlin
fun Int.evenOrNull() = takeUnless { it % 2 != 0 }
```
Example of **correct** code:

```kotlin
fun Int.evenOrNull() = takeIf { it % 2 == 0 }
```

## Further Reading

* [Detekt - DoubleNegativeLambda](https://detekt.dev/style.html#doublenegativelambda)