Pattern: Use of `?:`

Issue: -

## Description

Detects nullable boolean checks which use an elvis expression `?:` rather than equals `==`.

Per the [Kotlin coding conventions](https://kotlinlang.org/docs/coding-conventions.html#nullable-boolean-values-in-conditions)
converting a nullable boolean property to non-null should be done via `!= false` or `== true`
rather than `?: true` or `?: false` (respectively).

Example of **incorrect** code:

```kotlin
value ?: true
value ?: false
```

Example of **correct** code:

```kotlin
value != false
value == true
```

## Further Reading

* [Detekt - NullableBooleanCheck](https://detekt.dev/style.html#nullablebooleancheck)