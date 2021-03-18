Pattern: Utility class with public constructor

Issue: -

## Description

A class which only contains utility variables and functions with no concrete implementation can be refactored into an `object` or an class with a non-public constructor. Furthermore, this rule reports utility classes which are not `final`.

Example of **incorrect** code:

```kotlin
class UtilityClassViolation {

    // public constructor here
    constructor() {
        // ...
    }

    companion object {
        val i = 0
    }
}

open class UtilityClassViolation private constructor() {

    // ...
}
```

Example of **correct** code:

```kotlin
class UtilityClass {

    private constructor() {
        // ...
    }

    companion object {
        val i = 0
    }
}
object UtilityClass {

    val i = 0
}
```

## Further Reading

* [Detekt - UtilityClassWithPublicConstructor](https://detekt.github.io/detekt/style.html#utilityclasswithpublicconstructor)