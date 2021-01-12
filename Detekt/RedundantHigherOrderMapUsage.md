Pattern: Redundant map usage

Issue: -

## Description

Redundant maps add complexity to the code and accomplish nothing. They should be removed or replaced with the proper operator.

Example of **incorrect** code:

```kotlin
fun foo(list: List<Int>): List<Int> {
    return list
        .filter { it > 5 }
        .map { it }
}

fun bar(list: List<Int>): List<Int> {
    return list
        .filter { it > 5 }
        .map {
            doSomething(it)
            it
        }
}

fun baz(set: Set<Int>): List<Int> {
    return set.map { it }
}
```

Example of **correct** code:

```kotlin
fun foo(list: List<Int>): List<Int> {
    return list
        .filter { it > 5 }
}

fun bar(list: List<Int>): List<Int> {
    return list
        .filter { it > 5 }
        .onEach {
            doSomething(it)
        }
}

fun baz(set: Set<Int>): List<Int> {
    return set.toList()
}
```

## Further Reading

* [Detekt - RedundantHigherOrderMapUsage](https://detekt.github.io/detekt/style.html#redundanthigherordermapusage)