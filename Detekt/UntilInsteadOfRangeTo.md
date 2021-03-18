Pattern: Missing use of `until`

Issue: -

## Description

`until` is applicable in cases where the upper range value is described as some value subtracted by `1`. It helps to prevent off-by-one errors.

Example of **incorrect** code:

```kotlin
for (i in 0 .. 10 - 1) {}
val range = 0 .. 10 - 1
```

Example of **correct** code:

```kotlin
for (i in 0 until 10) {}
val range = 0 until 10
```

## Further Reading

* [Detekt - UntilInsteadOfRangeTo](https://detekt.github.io/detekt/style.html#untilinsteadofrangeto)