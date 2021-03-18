Pattern: Library code without explicit return type

Issue: -

## Description

Library functions/properties should have an explicit return type. Inferred return type can easily be changed by mistake which may lead to breaking changes.

Example of **incorrect** code:

```kotlin
// code from a library
val strs = listOf("foo, bar")
fun bar() = 5
class Parser {
     fun parse() = ...
}
```

Example of **correct** code:

```kotlin
// code from a library
val strs: List<String> = listOf("foo, bar")
fun bar(): Int = 5

class Parser {
     fun parse(): ParsingResult = ...
}
```

## Further Reading

* [Detekt - LibraryCodeMustSpecifyReturnType](https://detekt.github.io/detekt/style.html#librarycodemustspecifyreturntype)