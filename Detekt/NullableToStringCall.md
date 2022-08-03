Pattern: Nullable `toString` call

Issue: -

## Description

Turn on this rule to flag `toString` calls with a nullable receiver that may return the string `null`.

Example of **incorrect** code:

```kotlin
fun foo(a: Any?): String {
    return a.toString()
}

fun bar(a: Any?): String {
    return "$a"
}
```

Example of **correct** code:

```kotlin
fun foo(a: Any?): String {
    return a?.toString() ?: "-"
}

fun bar(a: Any?): String {
    return "${a ?: "-"}"
}
```

## Further Reading

* [Detekt - NullableToStringCall](https://detekt.dev/docs/rules/potential-bugs/#nullabletostringcall)