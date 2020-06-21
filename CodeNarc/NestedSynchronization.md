Pattern: Nested synchronization

Issue: -

## Description

Nested `synchronized` statements are either useless (if the lock objects are identical) or prone to deadlock.

Note that a *closure* or an *anonymous inner class* carries its own context (scope). A `synchronized` statement within a *closure* or an *anonymous inner class* defined within an outer `synchronized` statement does not cause a violation (though nested `synchronized` statements within either of those will).

Here is an example of code that produces a violation:

``` groovy
def someMethod() {
    synchronized(this) {
        // do something ...
        synchronized(this) {
            // do something else ...
        }
    }
}
```

## Further Reading

* [CodeNarc - NestedSynchronization](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#nestedsynchronization-rule)