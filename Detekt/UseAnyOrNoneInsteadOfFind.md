Pattern: Use of `find` instead of `any`/`none`

Issue: -

## Description

Turn on this rule to flag `find` calls for null check that can be replaced with a `any` or `none` call.

Example of **incorrect** code:

```kotlin
listOf(1, 2, 3).find { it == 4 } != null
listOf(1, 2, 3).find { it == 4 } == null
```

Example of **correct** code:

```kotlin
listOf(1, 2, 3).any { it == 4 }
listOf(1, 2, 3).none { it == 4 }
```

## Further Reading

* [Detekt - UseAnyOrNoneInsteadOfFind](https://detekt.dev/style.html#useanyornoneinsteadoffind)