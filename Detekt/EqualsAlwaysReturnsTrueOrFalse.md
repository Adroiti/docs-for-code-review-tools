Pattern: Constant return value for `equals()`

Issue: -

## Description

Reports `equals()` methods which will always return `true` or `false`. Equals methods should always report if some other object is equal to the current object.

Example of **incorrect** code:

```kotlin
override fun equals(other: Any?): Boolean {
    return true
}
```

Example of **correct** code:

```kotlin
override fun equals(other: Any?): Boolean {
    return this == other
}
```

## Further Reading

* [Detekt - EqualsAlwaysReturnsTrueOrFalse](https://arturbosch.github.io/detekt/potential-bugs.html#equalsalwaysreturnstrueorfalse)