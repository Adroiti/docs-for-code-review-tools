Pattern: Unnecessary use of `Unit`

Issue: -

## Description

It is not necessary to define a return type of `Unit` on functions or to specify a lone Unit statement. This rule detects and reports instances where the Unit return type is specified on functions and the occurrences of a lone `Unit` statement.

Example of **incorrect** code:

```kotlin
fun foo(): Unit {
    return Unit 
}
fun foo() = Unit

fun doesNothing() {
    Unit
}

```

Example of **correct** code:

```kotlin
fun foo() { }

// overridden no-op functions are allowed
override fun foo() = Unit

```

## Further Reading

* [Detekt - OptionalUnit](https://detekt.github.io/detekt/style.html#optionalunit)