Pattern: Missing `NoSuchElementException` for _Iterator_

Issue: -

## Description

Reports implementations of the _Iterator_ interface which do not throw a `NoSuchElementException` in the
implementation of the `next()` method. When there are no more elements to return an _Iterator_ should throw a
`NoSuchElementException`.

Example of **incorrect** code:

```kotlin
class MyIterator : Iterator<String> {

    override fun next(): String {
        return ""
    }
}
```

Example of **correct** code:

```kotlin
class MyIterator : Iterator<String> {

    override fun next(): String {
        if (!this.hasNext()) {
            throw NoSuchElementException()
        }
        // ...
    }
}
```

## Further Reading

* [Detekt - IteratorNotThrowingNoSuchElementException](https://detekt.dev/docs/rules/potential-bugs/#iteratornotthrowingnosuchelementexception)