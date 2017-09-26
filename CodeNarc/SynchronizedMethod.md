Pattern: Synchronized method

Issue: -

## Description

This rule reports uses of the `synchronized` keyword on methods. Synchronized methods are the same as synchronizing on `this`, which effectively make your synchronization policy public and modifiable by other objects. To avoid possibilities of deadlock, it is better to synchronize on internal objects.

Here is an example of code that produces a violation:

``` groovy
synchronized def myMethod() {
    // do stuff ...
}
```

## Further Reading

* [CodeNarc - SynchronizedMethod](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#SynchronizedMethod)