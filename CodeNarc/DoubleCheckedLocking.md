Pattern: Double checked locking

Issue: -

## Description

This rule detects double checked locking, where a `lock hint` is tested for `null` before initializing an object within a synchronized block. Double checked locking does not guarantee correctness and is an anti-pattern.

Example of violations:

``` groovy
if (object == null) {
    synchronized(this) {
        if (object == null) {
            // createObject() could be called twice depending
            // on the Thread Scheduler.
            object = createObject()
        }
    }
}

// there are several idioms to fix this problem.
def result = object;
if (result == null) {
    synchronized(this) {
        result = object;
        if (result == null)
            object = result = createObject()
    }
}

// and a better solution for a singleton:
class someClass  {
    private static class ObjectHolder {
       public static Object object = createObject()
    }
    public static Object getObject() {
        return ObjectHolder.object;
    }
}
```

## Further Reading

* [Wikipedia - Double-checked locking](https://en.wikipedia.org/wiki/Double-checked_locking#Usage_in_Java)
* [CodeNarc - DoubleCheckedLocking](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#doublecheckedlocking-rule)