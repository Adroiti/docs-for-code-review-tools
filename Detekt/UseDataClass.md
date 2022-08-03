Pattern: Missing use of `data class`
Issue: -

## Description

Classes that simply hold data should be refactored into a `data class`. Data classes are specialized to hold data
and generate `hashCode`, `equals` and `toString` implementations as well.

Example of **incorrect** code:

```kotlin
class DataClassCandidate(val i: Int) {

    val i2: Int = 0
}
```

Example of **correct** code:

```kotlin
data class DataClass(val i: Int, val i2: Int)
```

## Further Reading

* [Detekt - UseDataClass](https://detekt.dev/docs/rules/style/#usedataclass)