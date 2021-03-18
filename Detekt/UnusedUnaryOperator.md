Pattern: Unused unary operator

Issue: -

## Description

Detects unused unary operators.

Example of **incorrect** code:

```java
val x = 1 + 2
    + 3 + 4
println(x) // 3

```

Example of **correct** code:

```java
val x = 1 + 2 + 3 + 4
println(x) // 10

```

## Further Reading

* [Detekt - UnusedUnaryOperator](https://detekt.github.io/detekt/potential-bugs.html#unusedunaryoperator)