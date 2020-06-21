Pattern: Use of synchronized `readObject()`

Issue: -

## Description

Catches `Serializable` classes that define a synchronized `readObject()` method. By definition, an object created by deserialization is only reachable by one thread, and thus there is no need for `readObject()` to be synchronized. If the `readObject()` method itself is causing the object to become visible to another thread, that is an example of very dubious coding style.

Examples:

``` groovy
class SomeClass implements Serializable {

    private synchronized void readObject(ObjectInputStream input) throws IOException, ClassNotFoundException {
        // violation, no need to synchronized
    }
}

class SomeClass implements Serializable {

    private void readObject(ObjectInputStream input) throws IOException, ClassNotFoundException {
        synchronized(lock) {
            // violation, no need to synchronized
        }
    }
}

// OK, class not Serializable
class SomeClass {

    private synchronized void readObject(ObjectInputStream input) throws IOException, ClassNotFoundException { }
}

// OK, class not Serializable
class SomeClass {

    private void readObject(ObjectInputStream input) throws IOException, ClassNotFoundException {
        synchronized(lock) { }
    }
}

class SomeClass implements Serializable {

    private void readObject(ObjectInputStream input) throws IOException, ClassNotFoundException {
        // OK, this block is more than just a simple sync statement
        synchronized(lock) { }
        doSomething()
    }
}
```

## Further Reading

* [CodeNarc - SynchronizedReadObjectMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#synchronizedreadobjectmethod-rule)