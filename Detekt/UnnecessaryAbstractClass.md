Pattern: Unnecessary abstract class

Issue: -

## Description

In case an `abstract class` does not have any concrete members it should be refactored into an interface. Abstract classes which do not define any `abstract` members should instead be refactored into concrete classes.

Example of **incorrect** code:

```kotlin
abstract class OnlyAbstractMembersInAbstractClass { // violation: no concrete members

    abstract val i: Int
    abstract fun f()
}

abstract class OnlyConcreteMembersInAbstractClass { // violation: no abstract members

    val i: Int = 0
    fun f() { }
}
```

## Further Reading

* [Detekt - UnnecessaryAbstractClass](https://detekt.dev/docs/rules/style/#unnecessaryabstractclass)