Pattern: Use of `NotImplementedError` or `TODO(..)`

Issue: -

## Description

Reports all exceptions of the type `NotImplementedError` that are thrown. It also reports all `TODO(..)` functions. These indicate that functionality is still under development and will not work properly. Both of these should only serve as temporary declarations and should not be put into production environments.

Example of **incorrect** code:

```kotlin
fun foo() {
    throw NotImplementedError()
}

fun todo() {
    TODO("")
}
```

## Further Reading

* [Detekt - NotImplementedDeclaration](https://detekt.dev/docs/rules/exceptions/#notimplementeddeclaration)