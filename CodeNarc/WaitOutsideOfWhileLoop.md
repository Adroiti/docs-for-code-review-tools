Pattern: Wait outside of `while` loop

Issue: -

## Description

Calls to `Object.wait()` must be within a `while` loop. This ensures that the awaited condition has not already been satisfied by another thread before the `wait()` is invoked. It also ensures that the proper thread was resumed and guards against incorrect notification.

As a more modern and flexible alternative, consider using the Java *concurrency utilities* instead of `wait()` and `notify()`.

Example of violation:

``` groovy
class SomeClass {
    private data

    void processData()
        synchronized(data) {
            if (!data.isReady()) {
                data.wait()
            }
            data.calculateStatistics()
        }
    }
}
```

Example of correct usage:

``` groovy
class SomeClass {
    private data

    void processData()
        synchronized(data) {
            while (!data.isReady()) {
                data.wait()
            }
            data.calculateStatistics()
        }
    }
}
```

## Further Reading

* [SEI CERT Coding Standards - THI03-J. Always invoke wait() and await() methods inside a loop](https://www.securecoding.cert.org/confluence/display/java/THI03-J.+Always+invoke+wait()+and+await()+methods+inside+a+loop)
* [CodeNarc - WaitOutsideOfWhileLoop](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#WaitOutsideOfWhileLoop)