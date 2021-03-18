Pattern: Malformed `=` placement

Issue: -

## Description

Requires that the equals sign, when used for an expression style function, is on the same line as the
rest of the function signature.

Example of **incorrect** code:

```kotlin
fun stuff(): Int
		= 5

fun <V> foo(): Int where V : Int
		= 5
```

Example of **correct** code:

```kotlin
fun stuff() = 5

fun stuff() =
		foo.bar()

fun <V> foo(): Int where V : Int = 5
```

## Further Reading

* [Detekt - EqualsOnSignatureLine](https://detekt.github.io/detekt/style.html#equalsonsignatureline)