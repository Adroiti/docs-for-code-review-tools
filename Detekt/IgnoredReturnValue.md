Pattern: Ignored return value

Issue: -

## Description

Warns on instances where a function, annotated with either `@CheckReturnValue` or `@CheckResult`, returns a value but that value is not used in any way. The Kotlin compiler gives no warning for this scenario normally so that's the rationale behind this rule.
Example of **incorrect** code:

```kotlin
    returnsValue()
```

Example of **correct** code:

```kotlin
    if (42 == returnsValue()) {}
    val x = returnsValue()
```

## Further Reading

* [Detekt - IgnoredReturnValue](https://detekt.dev/docs/rules/potential-bugs/#ignoredreturnvalue)