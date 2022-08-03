Pattern: Malformed boolean property name

Issue: -

## Description

Reports when a boolean property doesn’t match a pattern.

Example of **incorrect** code (`allowedPattern`: `'^(is|has|are)'`):

```kotlin
val progressBar: Boolean = true
```

Example of **correct** code:

```kotlin
val hasProgressBar: Boolean = true
```

## Further Reading

* [Detekt - BooleanPropertyNaming](https://detekt.dev/docs/rules/naming/#booleanpropertynaming)