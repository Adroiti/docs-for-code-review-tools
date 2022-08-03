Pattern: Malformed cascading call wrapping

Issue: -

## Description

Requires that all chained calls are placed on a new line if a preceding one is.

Example of **incorrect** code:

```kotlin
foo()
  .bar().baz()
```

Example of **correct** code:

```kotlin
foo().bar().baz()

foo()
  .bar()
  .baz()
```

## Further Reading

* [Detekt - CascadingCallWrapping](https://detekt.dev/docs/rules/style/#cascadingcallwrapping)