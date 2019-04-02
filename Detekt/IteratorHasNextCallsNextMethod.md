Pattern: Use of `next()` inside `hasNext()` for _Iterator_

Issue: -

## Description

Verifies implementations of the _Iterator_ interface. The `hasNext()` method of an _Iterator_ implementation should not have any side effects.
This rule reports implementations that call the `next()` method of the _Iterator_ inside the `hasNext()` method.

Example of **incorrect** code:

```kotlin
class MyIterator : Iterator<String> {

    override fun hasNext(): Boolean {
        return next() != null
    }
}
```

## Further Reading

* [Detekt - IteratorHasNextCallsNextMethod](https://arturbosch.github.io/detekt/potential-bugs.html#iteratorhasnextcallsnextmethod)