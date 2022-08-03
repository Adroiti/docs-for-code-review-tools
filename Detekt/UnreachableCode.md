Pattern: Unreachable code

Issue: -

## Description

Code can be unreachable because it is behind `return`, `throw`, `continue` or `break` expressions. This unreachable code should be removed as it serves no purpose.

Example of **incorrect** code:

```kotlin
for (i in 1..2) {
    break
    println() // unreachable
}

throw IllegalArgumentException()
println() // unreachable

fun f() {
    return
    println() // unreachable
}
```

## Further Reading

* [Detekt - UnreachableCode](https://detekt.dev/docs/rules/potential-bugs/#unreachablecode)