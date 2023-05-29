Pattern: Unused private property

Issue: -

## Description

An unused private property can be removed to simplify the source file.

This rule also detects unused constructor parameters since these can become
properties of the class when they are declared with `val` or `var`.

Example of **incorrect** code:

```kotlin
class Foo {
  private val unused = "unused"
}
```

Example of **correct** code:

```kotlin
class Foo {
  private val used = "used"

  fun greet() {
    println(used)
  }
}
```

## Further Reading

* [Detekt - UnusedPrivateProperty](https://detekt.dev/style.html#unusedprivateproperty)