Pattern: Use of `protected` member in `final` class

Issue: -

## Description

Kotlin classes are `final` by default. Thus classes which are not marked as `open` should not contain any `protected` members. Consider using `private` or `internal` modifiers instead.

Example of **incorrect** code:

```kotlin
class ProtectedMemberInFinalClass {
    protected var i = 0
}
```

Example of **correct** code:

```kotlin
class ProtectedMemberInFinalClass {
    private var i = 0
}
```

## Further Reading

* [Detekt - ProtectedMemberInFinalClass](https://detekt.dev/docs/rules/style/#protectedmemberinfinalclass)