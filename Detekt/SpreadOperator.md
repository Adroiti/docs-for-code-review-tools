Pattern: Use of spread operator

Issue: -

## Description

Using a spread operator causes a full copy of the array to be created before calling a method. This has a very high performance penalty.

Example of **incorrect** code:

```kotlin
fun foo(strs: Array<String>) {
    bar(*strs)
}

fun bar(vararg strs: String) {
    strs.forEach { println(it) }
}
```

## Further Reading

* [Detekt - SpreadOperator](https://detekt.github.io/detekt/performance.html#spreadoperator)
* [Kotlin's hidden costs - Benchmarks](https://sites.google.com/a/athaydes.com/renato-athaydes/posts/kotlinshiddencosts-benchmarks)