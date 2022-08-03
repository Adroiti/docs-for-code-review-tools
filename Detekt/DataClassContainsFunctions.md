Pattern: Data class with function

Issue: -

## Description

Data classes should mainly be used to store data. This rule assumes that they should not contain any extra functions aside functions that help with converting objects from/to one another. Data classes will automatically have a generated `equals`, `toString` and `hashCode` function by the compiler.

Example of **incorrect** code:

```kotlin
data class DataClassWithFunctions(val i: Int) {
    fun foo() { }
}
```

## Further Reading

* [Detekt - DataClassContainsFunctions](https://detekt.dev/docs/rules/style/#dataclasscontainsfunctions)