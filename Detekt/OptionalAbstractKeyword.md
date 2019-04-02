Pattern: Unnecessary `abstract` modifier

Issue: -

## Description

This rule reports `abstract` modifiers which are unnecessary and can be removed.

Example of **incorrect** code:

```kotlin
abstract interface Foo { // abstract keyword not needed

    abstract fun x() // abstract keyword not needed
    abstract var y: Int // abstract keyword not needed
}
```

Example of **correct** code:

```kotlin
interface Foo {

    fun x()
    var y: Int
}
```

## Further Reading

* [Detekt - OptionalAbstractKeyword](https://arturbosch.github.io/detekt/style.html#optionalabstractkeyword)