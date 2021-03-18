Pattern: Unnecessary `abstract` modifier

Issue: -

## Description

`abstract` modifiers are unnecessary and can be removed.

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

* [Detekt - OptionalAbstractKeyword](https://detekt.github.io/detekt/style.html#optionalabstractkeyword)