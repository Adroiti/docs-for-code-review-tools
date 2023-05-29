Pattern: Cast of nullable to non-nullable type

Issue: -

## Description

Reports cast of nullable variable to non-null type. Cast like this can hide `null`
problems in your code. The compliant code would be that which will correctly check
 for two things (nullability and type) and not just one (cast).

Example of **incorrect** code:

```kotlin
fun foo(bar: Any?) {
    val x = bar as String
}
```

Example of **correct** code:

```kotlin
fun foo(bar: Any?) {
    val x = checkNotNull(bar) as String
}

// Alternative
fun foo(bar: Any?) {
    val x = (bar ?: error("null assertion message")) as String
}
```

## Further Reading

* [Detekt - CastNullableToNonNullableType](https://detekt.dev/potential-bugs.html#castnullabletononnullabletype)