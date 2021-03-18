Pattern: Use of `?: emptyList()`

Issue: -

## Description

Detects `?: emptyList()` that can be replaced with `orEmpty()` call.

Example of **incorrect** code:

```java
fun test(x: List<Int>?, s: String?) {
    val a = x ?: emptyList()
    val b = s ?: ""
}

```

Example of **correct** code:

```java
fun test(x: List<Int>?, s: String?) {
    val a = x.orEmpty()
    val b = s.orEmpty()
}

```

## Further Reading

* [Detekt - UseOrEmpty](https://detekt.github.io/detekt/style.html#useorempty)