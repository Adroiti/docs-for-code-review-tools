Pattern: Use of public library entity

Issue: -

## Description

Library typealias and classes should be internal or private.

Example of **incorrect** code:

```kotlin
// code from a library
class A
```

Example of **correct** code:

```kotlin
// code from a library
internal class A
```

## Further Reading

* [Detekt - LibraryEntitiesShouldNotBePublic](https://detekt.github.io/detekt/style.html#libraryentitiesshouldnotbepublic)