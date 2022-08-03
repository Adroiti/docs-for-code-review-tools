Pattern: Missing use of indexed access operator `[]`

Issue: -

## Description

Prefer the usage of the indexed access operator `[]` for map or list element access or insert methods.

Example of **incorrect** code:

```kotlin
 val map = Map<String, String>()
 map.put("key", "value")
 val value = map.get("key")
```

Example of **correct** code:

```kotlin
 val map = Map<String, String>()
 map["key"] = "value"
 val value = map["key"]
```

## Further Reading

* [Detekt - ExplicitCollectionElementAccessMethod](https://detekt.dev/docs/rules/style/#explicitcollectionelementaccessmethod)
* [Kotlin - Indexed access operator](https://kotlinlang.org/docs/reference/operator-overloading.html#indexed)