Pattern: Too many named arguments

Issue: -

## Description

Reports function invocations which have more parameters than a certain threshold and are all not named.

Example of **incorrect** code:

```kotlin
fun sum(a: Int, b: Int, c: Int, d: Int) {
}
sum(1, 2, 3, 4)
```

Example of **correct** code:

```kotlin
fun sum(a: Int, b: Int, c: Int, d: Int) {
}
sum(a = 1, b = 2, c = 3, d = 4)
```

## Further Reading

* [Detekt - NamedArguments](https://detekt.dev/docs/rules/complexity/#namedarguments)