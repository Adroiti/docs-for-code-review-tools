Pattern: Missing use of `sumOf`

Issue: -

## Description

Turn on this rule to flag `flatMap` and `size/count` calls that can be replaced with a `sumOf` call.

Example of **incorrect** code:

```kotlin
class Foo(val foo: List<Int>)
list.flatMap { it.foo }.size
list.flatMap { it.foo }.count()
list.flatMap { it.foo }.count { it > 2 }
listOf(listOf(1), listOf(2, 3)).flatten().size
```

Example of **correct** code:

```kotlin
list.sumOf { it.foo.size }
list.sumOf { it.foo.count() }
list.sumOf { it.foo.count { foo -> foo > 2 } }
listOf(listOf(1), listOf(2, 3)).sumOf { it.size }
```

## Further Reading

* [Detekt - UseSumOfInsteadOfFlatMapSize](https://detekt.dev/style.html#usesumofinsteadofflatmapsize)