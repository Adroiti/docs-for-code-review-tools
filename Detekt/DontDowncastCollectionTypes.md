Pattern: Down-casting collection type

Issue: -

## Description

Down-casting immutable types from `kotlin.collections` should be discouraged. The result of the downcast is platform specific and can lead to unexpected crashes. Prefer to use instead the `toMutable<Type>()` functions.

Example of **incorrect** code:

```java
val list : List<Int> = getAList()
if (list is MutableList) {
    list.add(42)
}

(list as MutableList).add(42)
```

Example of **correct** code:

```java
val list : List<Int> = getAList()
list.toMutableList().add(42)
```

## Further Reading

* [Detekt - DontDowncastCollectionTypes](https://detekt.dev/docs/rules/potential-bugs/#dontdowncastcollectiontypes)