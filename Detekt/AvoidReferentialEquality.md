Pattern: Use of referential equality

Issue: -

## Description

Kotlin supports two types of equality: structural equality and referential equality. While there are use cases for both, checking for referential equality for some types (such as `String` or `List`) is likely not intentional and may case unexpected results.

Example of **incorrect** code:

```kotlin
val areEqual = "aString" === otherString
val areNotEqual = "aString" !== otherString
```

Example of **correct** code:

```kotlin
val areEqual = "aString" == otherString
val areNotEqual = "aString" != otherString
```

## Further Reading

* [Detekt - AvoidReferentialEquality](https://detekt.github.io/detekt/potential-bugs.html#avoidreferentialequality)