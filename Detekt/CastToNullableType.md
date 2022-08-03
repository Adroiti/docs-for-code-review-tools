Pattern: Cast to nullable type

Issue: -

## Description

There are cases where `as String?` is misused as the safe cast (`as? String`), so if you want to prevent those cases, turn on this rule.

Example of **incorrect** code:

```java
fun foo(a: Any?) {
    val x: String? = a as String? // If 'a' is not String, ClassCastException will be thrown.
}
```

Example of **correct** code:

```java
fun foo(a: Any?) {
    val x: String? = a as? String
}
```

## Further Reading

* [Detekt - CastToNullableType](https://detekt.dev/docs/rules/potential-bugs/#casttonullabletype)