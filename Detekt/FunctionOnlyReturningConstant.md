Pattern: Function only returning constant

Issue: -

## Description

A function that only returns a single constant can be misleading. Instead prefer to define the constant directly as a `const val`.

Example of **incorrect** code:

```kotlin
fun functionReturningConstantString() = "1"
```

Example of **correct** code:

```kotlin
const val constantString = "1"
```

## Further Reading

* [Detekt - FunctionOnlyReturningConstant](https://arturbosch.github.io/detekt/style.html#functiononlyreturningconstant)