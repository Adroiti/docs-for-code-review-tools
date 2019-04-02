Pattern: Use of magic number

Issue: -

## Description

This rule detects and reports usages of magic numbers in the code. Prefer defining constants with clear names describing what the magic number means.

Example of **incorrect** code:

```kotlin
class User {

    fun checkName(name: String) {
        if (name.length > 42) {
            throw IllegalArgumentException("username is too long")
        }
        // ...
    }
}
```

Example of **correct** code:

```kotlin

class User {

    fun checkName(name: String) {
        if (name.length > MAX_USERNAME_SIZE) {
            throw IllegalArgumentException("username is too long")
        }
        // ...
    }

    companion object {
        private const val MAX_USERNAME_SIZE = 42
    }
}
```

## Further Reading

* [Detekt - MagicNumber](https://arturbosch.github.io/detekt/style.html#magicnumber)