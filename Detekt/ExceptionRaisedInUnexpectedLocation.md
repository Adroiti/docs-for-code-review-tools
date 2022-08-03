Pattern: Exception raised in unexpected location

Issue: -

## Description

This rule allows to define functions which should never throw an exception. If a function exists that does throw an exception it will be reported. By default this rule is checking for `toString`, `hashCode`, `equals` and `finalize`. This rule is configurable via the `methodNames` configuration to change the list of functions which should not throw any exceptions.

Example of **incorrect** code:

```kotlin
class Foo {

    override fun toString(): String {
        throw IllegalStateException() // exception should not be thrown here
    }
}
```

## Further Reading

* [Detekt - ExceptionRaisedInUnexpectedLocation](https://detekt.dev/docs/rules/exceptions/#exceptionraisedinunexpectedlocation)