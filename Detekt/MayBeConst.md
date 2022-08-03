Pattern: Missing use of `const val`

Issue: -

## Description

Identifies and reports properties (`val`) that may be `const val` instead. Using `const val` can lead to better performance of the resulting bytecode as well as better interoperability with Java.

Example of **incorrect** code:

```kotlin
val myConstant = "abc"
```

Example of **correct** code:

```kotlin
const val MY_CONSTANT = "abc"
```

## Further Reading

* [Detekt - MayBeConst](https://detekt.dev/docs/rules/style/#maybeconst)