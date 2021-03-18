Pattern: Use of `equals()` to compare value with `null`

Issue: -

## Description

To compare an object with `null` prefer using `==`. This rule detects and reports instances in the code where the `equals()` method is used to compare a value with `null`.

Example of **incorrect** code:

```kotlin
fun isNull(str: String) = str.equals(null)
```

Example of **correct** code:

```kotlin
fun isNull(str: String) = str == null
```

## Further Reading

* [Detekt - EqualsNullCall](https://detekt.github.io/detekt/style.html#equalsnullcall)