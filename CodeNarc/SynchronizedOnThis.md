Pattern: Synchronized on `this`

Issue: -

## Description

This rule reports uses of the `synchronized` blocks where the synchronization reference is `this`. Doing this effectively makes your synchronization policy public and modifiable by other objects. To avoid possibilities of deadlock, it is better to synchronize on internal objects.

Here is an example of code that produces a violation:

``` groovy
def method3() {
    synchronized(this) {
        // do stuff ...
    }
}
```

## Further Reading

* [CodeNarc - SynchronizedOnThis](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#SynchronizedOnThis)