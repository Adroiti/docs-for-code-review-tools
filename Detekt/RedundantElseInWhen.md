Pattern: Redundant `else` in `when`

Issue: -

## Description

Turn on this rule to flag `when` expressions that contain a redundant `else` case. This occurs when it can be
verified that all cases are already covered when checking cases on an enum or sealed class.

Example of **incorrect** code:

```kotlin
enum class Color {
    RED,
    GREEN,
    BLUE
}

fun whenOnEnumFail(c: Color) {
    when(c) {
        Color.BLUE -> {}
        Color.GREEN -> {}
        Color.RED -> {}
        else -> {}
    }
}
```

Example of **correct** code:

```kotlin
enum class Color {
    RED,
    GREEN,
    BLUE
}

fun whenOnEnumCompliant(c: Color) {
    when(c) {
        Color.BLUE -> {}
        Color.GREEN -> {}
        else -> {}
    }
}

fun whenOnEnumCompliant2(c: Color) {
    when(c) {
        Color.BLUE -> {}
        Color.GREEN -> {}
        Color.RED -> {}
    }
}
```

## Further Reading

* [Detekt - RedundantElseInWhen](https://detekt.dev/docs/rules/potential-bugs/#redundantelseinwhen)