Pattern: Missing use of `requireNotNull`

Issue: -

## Description

Flags `require` calls for not-null check that can be replaced with a `requireNotNull` call.

Example of **incorrect** code:

```kotlin
require(x != null)
```

Example of **correct** code:

```kotlin
requireNotNull(x)
```

## Further Reading

* [Detekt - UseRequireNotNull](https://detekt.dev/docs/rules/style/#UseRequireNotNull)