Pattern: Duplicate case in `when` expression

Issue: -

## Description

Flags duplicate case statements in `when` expressions.

If a `when` expression contains the same case statement multiple times they should be merged. Otherwise it might be
easy to miss one of the cases when reading the code, leading to unwanted side effects.

Example of **incorrect** code:

```kotlin
when (i) {
    1 -> println("one")
    1 -> println("one")
    else -> println("else")
}
```

Example of **correct** code:

```kotlin
when (i) {
    1 -> println("one")
    else -> println("else")
}
```

## Further Reading

* [Detekt - DuplicateCaseInWhenExpression](https://detekt.github.io/detekt/potential-bugs.html#duplicatecaseinwhenexpression)