Pattern: Use of `lateinit`

Issue: -

## Description

Using `lateinit` for property initialization can be error prone and the actual initialization is not guaranteed. Try using constructor injection or delegation to initialize properties.

Example of **incorrect** code:

```kotlin
class Foo {
    @JvmField lateinit var i1: Int
    @JvmField @SinceKotlin("1.0.0") lateinit var i2: Int
}
```

## Further Reading

* [Detekt - LateinitUsage](https://arturbosch.github.io/detekt/potential-bugs.html#lateinitusage)