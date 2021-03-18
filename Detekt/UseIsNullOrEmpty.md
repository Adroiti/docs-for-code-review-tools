Pattern: Missing use of `isNullOrEmpty()`

Issue: -

## Description

Detects null or empty checks that can be replaced with `isNullOrEmpty()` call.

Example of **incorrect** code:

```java
fun foo(x: List<Int>?) {
    if (x == null || x.isEmpty()) return
}
fun bar(x: List<Int>?) {
    if (x == null || x.count() == 0) return
}
fun baz(x: List<Int>?) {
    if (x == null || x.size == 0) return
}
```

Example of **correct** code:

```java
if (x.isNullOrEmpty()) return
```

## Further Reading

* [Detekt - UseIsNullOrEmpty](https://detekt.github.io/detekt/style.html#useisnullorempty)