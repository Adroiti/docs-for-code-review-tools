Pattern: Use of `finalize()` method

Issue: -

## Description

Finalizers are unpredictable, often dangerous, and generally unnecessary. Their use can cause erratic behavior, poor performance, and portability problems. Finalizers have a few valid uses, but as a rule of thumb, you should avoid them.

Provide an explicit termination method for a class whose objects encapsulate resources that require termination, such as files or threads. Typical examples of explicit termination methods are the `close` methods on `InputStream`, `OutputStream`, and `java.sql.Connection`. Another example is the `cancel` method on `java.util.Timer`, which performs the necessary state change to cause the thread associated with a `Timer` instance to terminate itself gently. 

Explicit termination methods are typically used in combination with the `try-finally` construct to ensure termination. Invoking the explicit termination method inside the `finally` clause ensures that it will get executed even if an exception is thrown while the object is being used:


```java
// try-finally block guarantees execution of termination method
Foo foo = new Foo(...);
try {
    // Do what must be done with foo
    ...
} finally {
    foo.terminate();  // Explicit termination method
}
```


If you must use finalizers, there are a few guidelines you can follow that will help contain the damage. Limit the number of finalizeable objects, which will minimize the number of objects that have to incur the allocation and collection costs of finalization. Organize your classes so that finalizeable objects hold no other data, which will minimize the amount of memory tied up in finalizeable objects after they become unreachable, as there can be a long delay before they are actually reclaimed. In particular, beware when extending finalizeable classes from standard libraries.

## Default configuration

To configure the check: 


```xml
<module name="NoFinalizer"/>
```

## Further Reading

* [Effective Java, 2nd Edition - Item 7: Avoid finalizers](http://www.informit.com/articles/article.aspx?p=1216151&seqNum=7)
* [Tony Printezis - How to Handle Java Finalization's Memory-Retention Issues](http://www.oracle.com/technetwork/java/javamail/finalization-137655.html)
* [IBM developerWorks - Garbage collection and performance](https://www.ibm.com/developerworks/java/library/j-jtp01274/index.html)
* [Google Java Style Guide - Finalizers: not used](https://google.github.io/styleguide/javaguide.html#s6.4-finalizers)
* [checkstyle - NoFinalizer](http://checkstyle.sourceforge.net/config_coding.html#NoFinalizer)
