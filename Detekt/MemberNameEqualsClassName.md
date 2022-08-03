Pattern: Member name equals class name

Issue: -

## Description

Reports a member that has the same name as the containing class or object. This might result in confusion. The member should either be renamed or changed to a constructor. Factory functions that create an instance of the class are exempt from this rule.

Example of **incorrect** code:

```kotlin
class MethodNameEqualsClassName {

    fun methodNameEqualsClassName() { }
}

class PropertyNameEqualsClassName {

    val propertyEqualsClassName = 0
}
```

Example of **correct** code:

```kotlin
class Manager {

    companion object {
        // factory functions can have the same name as the class
        fun manager(): Manager {
            return Manager()
        }
    }
}
```

## Further Reading

* [Detekt - MemberNameEqualsClassName](https://detekt.dev/docs/rules/naming/#membernameequalsclassname)