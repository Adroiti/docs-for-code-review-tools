Pattern: Duplicated `String` literal

Issue: -

## Description

Repeatedly typing out the same `String` literal across the codebase makes it harder to change and maintain.

Prefer extracting the String literal into a property or constant instead.

Example of **incorrect** code:

```kotlin
class Foo {

    val s1 = "lorem"
    fun bar(s: String = "lorem") {
        s1.equals("lorem")
    }
}
```

Example of **correct** code:

```kotlin
class Foo {
    val lorem = "lorem"
    val s1 = lorem
    fun bar(s: String = lorem) {
        s1.equals(lorem)
    }
}
```

## Further Reading

* [Detekt - StringLiteralDuplication](https://detekt.dev/docs/rules/complexity/#stringliteralduplication)