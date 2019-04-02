Pattern: Missing override for `equals()` or `hashCode()`

Issue: -

## Description

When a class overrides the `equals()` method it should also override the `hashCode()` method.

All hash-based collections depend on objects meeting the equals-contract. Two equal objects must produce the same hashcode. When inheriting equals or hashcode, override the inherited and call the super method for clarification.

Example of **incorrect** code:

```kotlin
class Foo {

    override fun equals(other: Any?): Boolean {
        return super.equals(other)
    }
}
```

Example of **correct** code:

```kotlin
class Foo {

    override fun equals(other: Any?): Boolean {
        return super.equals(other)
    }

    override fun hashCode(): Int {
        return super.hashCode()
    }
}
```

## Further Reading

* [Detekt - EqualsWithHashCodeExist](https://arturbosch.github.io/detekt/potential-bugs.html#equalswithhashcodeexist)