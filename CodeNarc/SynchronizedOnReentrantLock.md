Pattern: Synchronized on `ReentrantLock`

Issue: -

## Description

Synchronizing on a `ReentrantLock` field is almost never the intended usage. A `ReentrantLock` should be obtained using the `lock()` method and released in a `finally` block using the `unlock()` method.

Here is the proper usage of `ReentrantLock`:

``` groovy
import java.util.concurrent.locks.ReentrantLock;
final lock = new ReentrantLock();
def method()  {
   //Trying to enter the critical section
   lock.lock(); // will wait until this thread gets the lock
   try {
      // critical section
   } finally {
      //releasing the lock so that other threads can get notifies
      lock.unlock();
   }
}
```

Example of violations:

``` groovy
class SomeClass {

    final ReentrantLock lock = new ReentrantLock()

    def method() {
        // violation
        synchronized(lock) { }
    }
}

class SomeClass {

    final ReentrantLock lock = new ReentrantLock()

    class SomeInnerClass {
        def method() {
            synchronized(lock) { }
        }
    }
}

class SomeClass {
    // implicit typing
    final def lock = new ReentrantLock()

    def method() {
        // violation
        synchronized(lock) { }
    }
}

class SomeClass {
    // implicit typing
    final def lock = new Object[0] // correct idiom

    def method() {
        return new Runnable() {
            final def lock = new ReentrantLock() // shadows parent from inner class
            public void run() {
                // violation
                synchronized(lock) { }
            }
        }
    }
}

class SomeClass {
    // implicit typing
    final def lock = new Object[0] // correct idiom

    class SomeInnerClass {

        final def lock = new ReentrantLock() // shadows parent from inner class
        def method() {
            // violation
            synchronized(lock) { }
        }
    }
}
```

## Further Reading

* [SlideShare - Java Concurrency Gotchas](http://www.slideshare.net/alexmiller/java-concurrency-gotchas-3666977)
* [CodeNarc - SynchronizedOnReentrantLock](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#synchronizedonreentrantlock-rule)