Pattern: Use of `forEach` on range

Issue: -

## Description

Using the `forEach` method on ranges has a heavy performance cost. Prefer using simple `for` loops.

Benchmarks have shown that using forEach on a range can have a huge performance cost in comparison to simple for loops. Hence in most contexts a simple for loop should be used instead.

Example of **incorrect** code:

```kotlin
(1..10).forEach {
    println(it)
}
(1 until 10).forEach {
    println(it)
}
(10 downTo 1).forEach {
    println(it)
}
```

Example of **correct** code:

```kotlin
for (i in 1..10) {
    println(i)
}
```

## Further Reading

* [Detekt - ForEachOnRange](https://detekt.dev/docs/rules/performance/#foreachonrange)
* [Kotlin's hidden costs - Benchmarks](https://sites.google.com/a/athaydes.com/renato-athaydes/posts/kotlinshiddencosts-benchmarks)