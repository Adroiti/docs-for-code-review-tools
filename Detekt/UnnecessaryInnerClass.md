Pattern: Unnecessary inner class

Issue: -

## Description

This rule reports unnecessary inner classes. Nested classes that do not access members from the outer class do not require the `inner` qualifier.

Example of **incorrect** code:

```kotlin
class A {
    val foo = "BAR"

    inner class B {
        val fizz = "BUZZ"

        fun printFizz() {
            println(fizz)
        }
    }
}
```

## Further Reading

* [Detekt - UnnecessaryInnerClass](https://detekt.dev/docs/rules/style/#unnecessaryinnerclass)