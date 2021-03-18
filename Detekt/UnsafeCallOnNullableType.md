Pattern: Unsafe call on nullable type

Issue: -

## Description

Reports unsafe calls on nullable types. These calls will throw a `NullPointerException` in case the nullable value is null. Kotlin provides many ways to work with nullable types to increase null safety. Guard the code appropriately to prevent null pointer exceptions.

Example of **incorrect** code:

```kotlin
fun foo(str: String?) {
    println(str!!.length)
}
```

Example of **correct** code:

```kotlin
fun foo(str: String?) {
    println(str?.length)
}
```

## Further Reading

* [Detekt - UnsafeCallOnNullableType](https://detekt.github.io/detekt/potential-bugs.html#unsafecallonnullabletype)