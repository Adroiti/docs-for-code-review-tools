Pattern: Unnecessary `.?`

Issue: -

## Description

Reports unnecessary safe call operators (`.?`) that can be removed by the user.

Example of **incorrect** code:

```kotlinval a: String = ""
val b = someValue?.length```
Example of **correct** code:

```kotlinval a: String? = null
val b = someValue?.length```

## Further Reading

* [Detekt - UnnecessarySafeCall](https://detekt.github.io/detekt/potential-bugs.html#unnecessarysafecall)