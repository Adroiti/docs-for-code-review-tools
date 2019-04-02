Pattern: Missing `serialVersionUID` for `Serializable` class

Issue: -

## Description

Classes which implement the `Serializable` interface should also correctly declare a `serialVersionUID`. This rule verifies that a `serialVersionUID` was correctly defined.

Example of **incorrect** code:

```kotlin
class IncorrectSerializable : Serializable {

    companion object {
        val serialVersionUID = 1 // wrong declaration for UID
    }
}
```

Example of **correct** code:

```kotlin
class CorrectSerializable : Serializable {

    companion object {
        const val serialVersionUID = 1L
    }
}
```

## Further Reading

* [Detekt - SerialVersionUIDInSerializableClass](https://arturbosch.github.io/detekt/style.html#serialversionuidinserializableclass)