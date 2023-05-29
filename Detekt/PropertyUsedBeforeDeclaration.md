Pattern: Property used before declaration

Issue: -

## Description

Reports properties that are used before declaration.

Example of **incorrect** code:

```kotlin
class C {
    private val number
        get() = if (isValid) 1 else 0

    val list = listOf(number)

    private val isValid = true
}

fun main() {
    println(C().list) // [0]
}
```

Example of **correct** code:

```kotlin
class C {
    private val isValid = true

    private val number
        get() = if (isValid) 1 else 0

    val list = listOf(number)
}

fun main() {
    println(C().list) // [1]
}
```

## Further Reading

* [Detekt - PropertyUsedBeforeDeclaration](https://detekt.dev/potential-bugs.html#propertyusedbeforedeclaration)