Pattern: Use of `var` when declaring mutable collection

Issue: -

## Description

Using `var` when declaring a mutable collection leads to double mutability. Consider instead declaring your variable with `val` or switching your declaration to use an immutable type.

Example of **incorrect** code:

```java
var myList = mutableListOf(1,2,3)
var mySet = mutableSetOf(1,2,3)
var myMap = mutableMapOf("answer" to 42)
```

Example of **correct** code:

```java
// Use val
val myList = mutableListOf(1,2,3)
val mySet = mutableSetOf(1,2,3)
val myMap = mutableMapOf("answer" to 42)

// Use immutable types
var myList = listOf(1,2,3)
var mySet = setOf(1,2,3)
var myMap = mapOf("answer" to 42)
```

## Further Reading

* [Detekt - DoubleMutabilityForCollection](https://detekt.github.io/detekt/potential-bugs.html#doublemutabilityforcollection)