Pattern: Unconditional jump statement in loop

Issue: -

## Description

Reports loops which contain jump statements that jump regardless of any conditions. This implies that the loop is only executed once and thus could be rewritten without a loop altogether.

Example of **incorrect** code:

```kotlin
for (i in 1..2) break
```

Example of **correct** code:

```kotlin
for (i in 1..2) {
    if (i == 1) break
}
```

## Further Reading

* [Detekt - UnconditionalJumpStatementInLoop](https://arturbosch.github.io/detekt/potential-bugs.html#unconditionaljumpstatementinloop)