Pattern: Use of KDoc comment for non-public prop

Issue: -

## Description

This rule will report any KDoc comments that refer to non-public properties of a class.
Clients do not need to know the implementation details.

Example of **incorrect** code:

```kotlin
/**
* Comment
* [prop1] - non-public property
* [prop2] - public property
*/
class Test {
    private val prop1 = 0
    val prop2 = 0
}
```

Example of **correct** code:

```kotlin
/**
* Comment
* [prop2] - public property
*/
class Test {
    private val prop1 = 0
    val prop2 = 0
}
```

## Further Reading

* [Detekt - KDocReferencesNonPublicProperty](https://detekt.dev/comments.html#kdocreferencesnonpublicproperty)