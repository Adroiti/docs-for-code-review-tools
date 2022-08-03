Pattern: Too many chained calls on same line

Issue: -

## Description

Limits the number of chained calls which can be placed on a single line.

Example of **incorrect** code:

```kotlin
a().b().c().d().e().f()
```

Example of **correct** code:

```kotlin
a().b().c()
  .d().e().f()
```

## Further Reading

* [Detekt - MaxChainedCallsOnSameLine](https://detekt.dev/style.html#maxchainedcallsonsameline)