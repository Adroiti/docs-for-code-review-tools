Pattern: Use of nullable variable

Issue: -

## Description

This rule inspects variables marked as nullable and reports which could be
declared as non-nullable instead.

Example of **incorrect** code:

```kotlin
class A {
    var a: Int? = 5

    fun foo() {
        a = 6
    }
}

class A {
    val a: Int?
        get() = 5
}

fun foo(a: Int?) {
    val b = a!! + 2
}

fun foo(a: Int?) {
    if (a != null) {
        println(a)
    }
}
```

Example of **correct** code:

```kotlin
class A {
    var a: Int = 5

    fun foo() {
        a = 6
    }
}

class A {
    val a: Int
        get() = 5
}

fun foo(a: Int) {
    val b = a + 2
}

fun foo(a: Int) {
    println(a)
}
```

## Further Reading

* [Detekt - CanBeNonNullable](https://detekt.dev/docs/rules/style/#canbenonnullable)