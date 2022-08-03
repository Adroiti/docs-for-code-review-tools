Pattern: Use of `Array<Primitive>`

Issue: -

## Description

Using `Array<Primitive>` leads to implicit boxing and performance hit. Prefer using Kotlin specialized Array
Instances.

As stated in the [documention](https://kotlinlang.org/docs/reference/basic-types.html#arrays), Kotlin has
specialized arrays to represent primitive types without boxing overhead, such as `IntArray`, `ByteArray` and so on.

Example of **incorrect** code:

```kotlin
fun function(array: Array<Int>) { }

fun returningFunction(): Array<Double> { }
```

Example of **correct** code:

```kotlin
fun function(array: IntArray) { }

fun returningFunction(): DoubleArray { }
```

## Further Reading

* [Detekt - ArrayPrimitive](https://detekt.dev/docs/rules/performance/#arrayprimitive)