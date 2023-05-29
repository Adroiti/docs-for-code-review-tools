Pattern: Missing use of `?.let {}`

Issue: -

## Description

`if` expressions that either check for not-null and return `null` in the false case or check for `null` and returns
`null` in the truthy case are better represented as `?.let {}` blocks.

Example of **incorrect** code:

```kotlin
if (x != null) { x.transform() } else null
if (x == null) null else y
```

Example of **correct** code:

```kotlin
x?.let { it.transform() }
x?.let { y }
```

## Further Reading

* [Detekt - UseLet](https://detekt.dev/style.html#uselet)