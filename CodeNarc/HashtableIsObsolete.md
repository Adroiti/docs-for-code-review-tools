Pattern: Use of `Hashtable`

Issue: -

## Description

Checks for references to the (*effectively*) obsolete `java.util.Hashtable` class. Use the **Java Collections Framework** classes instead, including `HashMap` or `ConcurrentHashMap`. See the JDK javadoc.

Note: As of the Java 2 platform v1.2, this class was retrofitted to implement the `Map` interface, making it a member of the Java Collections Framework. Unlike the new collection implementations, `Hashtable` is synchronized. If a thread-safe implementation is not needed, it is recommended to use `HashMap` in place of `Hashtable`. If a thread-safe highly-concurrent implementation is desired, then it is recommended to use `ConcurrentHashMap` in place of `Hashtable`.

Example of violations:

``` groovy
def someMap = new Hashtable()           // violation
```

## Further Reading

* [Java API Specification - Hashtable](https://docs.oracle.com/javase/7/docs/api/java/util/Hashtable.html)
* [CodeNarc - HashtableIsObsolete](http://codenarc.sourceforge.net/codenarc-rules-convention.html#HashtableIsObsolete)