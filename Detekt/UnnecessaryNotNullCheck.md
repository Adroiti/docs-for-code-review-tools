Pattern: Unnecessary not-null check

Issue: -

## Description

Reports unnecessary not-null checks with `requireNotNull` or `checkNotNull` that can be removed by the user.

Example of **incorrect** code:

```kotlin
var string = "foo"
println(requireNotNull(string))
```

Example of **correct** code:

```kotlin
var string : String? = "foo"
println(requireNotNull(string))
```

## Further Reading

* [Detekt - UnnecessaryNotNullCheck](https://detekt.dev/potential-bugs.html#unnecessarynotnullcheck)