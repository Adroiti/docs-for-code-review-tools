Pattern: Wrong class content order

Issue: -

## Description

Ensures class contents are ordered as follows as recommended by the Kotlin Coding Conventions:
- Property declarations and initializer blocks
- Secondary constructors
- Method declarations
- Companion object


Example of **incorrect** code:

```kotlin
class OutOfOrder {
    companion object {
        const val IMPORTANT_VALUE = 3
    }

    fun returnX(): Int {
        return x
    }

    private val x = 2
}

```

Example of **correct** code:

```kotlin
class InOrder {
    private val x = 2

    fun returnX(): Int {
        return x
    }

    companion object {
        const val IMPORTANT_VALUE = 3
    }
}
```

## Further Reading

* [Detekt - ClassOrdering](https://detekt.dev/docs/rules/style/#classordering)