Pattern: Incorrect `equals()` type parameter

Issue: -

## Description

Reports `equals()` methods which take in a wrongly typed parameter. Correct implementations of the `equals()` method should only take in a parameter of type `Any?`.

Example of **incorrect** code:

```kotlin
class Foo {

    fun equals(other: String): Boolean {
        return super.equals(other)
    }
}
```

Example of **correct** code:

```kotlin
class Foo {

    fun equals(other: Any?): Boolean {
        return super.equals(other)
    }
}
```

## Further Reading

* [Detekt - WrongEqualsTypeParameter](https://arturbosch.github.io/detekt/potential-bugs.html#wrongequalstypeparameter)