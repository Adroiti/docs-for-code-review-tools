Pattern: Synchronized on string

Issue: -

## Description

Synchronization on a `String` field can lead to deadlock. Constant strings are interned and shared across all other classes loaded by the JVM. Thus, this could is locking on something that other code might also be locking. This could result in very strange and hard to diagnose blocking and deadlock behavior.

Examples:

``` groovy
class MyClass {

    final String stringLock = "stringLock"

    def method() {
        // violation
        synchronized(stringLock) { }
    }
}

class MyClass {

    final String stringLock = "stringLock"

    class MyInnerClass {
        def method() {
            synchronized(stringLock) { }
        }
    }
}

class MyClass {
    // implicit typing
    final def stringLock = "stringLock"

    def method() {
        // violation
        synchronized(stringLock) { }
    }
}

class MyClass {
    // implicit typing
    final def lock = new Object[0] // correct idiom

    def method() {
        return new Runnable() {
            final def lock = "" // shadows parent from inner class
            public void run() {
                // violation
                synchronized(stringLock) { }
            }
        }
    }
}

class MyClass {
    // implicit typing
    final def lock = new Object[0] // correct idiom

    class MyInnerClass {

        final def lock = "" // shadows parent from inner class
        def method() {
            // violation
            synchronized(stringLock) { }
        }
    }
}
```

## Further Reading

* [CodeNarc - SynchronizedOnString](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#SynchronizedOnString)