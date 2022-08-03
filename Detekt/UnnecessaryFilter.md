Pattern: Unnecessary filter

Issue: -

## Description

Unnecessary filters add complexity to the code and accomplish nothing. They should be removed.

Example of **incorrect** code:

```java
val x = listOf(1, 2, 3)
    .filter { it > 1 }
    .count()

val x = listOf(1, 2, 3)
    .filter { it > 1 }
    .isEmpty()

```

Example of **correct** code:

```java
val x = listOf(1, 2, 3)
    .count { it > 2 }
}

val x = listOf(1, 2, 3)
    .none { it > 1 }

```

## Further Reading

* [Detekt - UnnecessaryFilter](https://detekt.dev/docs/rules/style/#unnecessaryfilter)