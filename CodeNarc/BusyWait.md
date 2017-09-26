Pattern: Busy wait

Issue: -

## Description

Busy waiting (forcing a `Thread.sleep()` while waiting on a condition) should be avoided. Prefer using the gate and barrier objects in the `java.util.concurrent` package.

Example of violations:

``` groovy
while (x) { Thread.sleep(1000) }
while (x) { Thread.sleep(1000) { /* interruption handler */} }
for (int x = 10; x; x--) {
    sleep(1000)     // sleep is added to Object in Groovy
}

// here is the proper way to wait:
countDownLatch.await()

// this is weird code to write, but does not cause a violation
for (def x : collections) {
    sleep(1000)
}

while (x) {
    // you should use a lock here, but technically you are
    // not just busy waiting because you are doing other work
    doSomething()
    sleep(1000)
}
```

## Further Reading

* [CodeNarc - BusyWait](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#BusyWait)