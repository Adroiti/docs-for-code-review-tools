Pattern: Use of `when` expression

Issue: -

## Description

Binary expressions are better expressed using an `if` expression than a `when` expression.

Example of **incorrect** code:

```kotlinwhen (x) {  null -> true  else -> false}```
Example of **correct** code:

```kotlinif (x == null) true else false```

## Further Reading

* [Detekt - UseIfInsteadOfWhen](https://detekt.github.io/detekt/style.html#useifinsteadofwhen)
* [Kotlin Coding Conventions](https://kotlinlang.org/docs/reference/coding-conventions.html#if-versus-when)