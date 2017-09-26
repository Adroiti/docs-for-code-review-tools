Pattern: `ThreadLocal` not `static` and `final`

Issue: -

## Description

This rule reports definition of the `ThreadLocal` fields that are not `static` and `final`.

*ThreadLocal* fields should be `static` and `final`. In the most common case a `java.lang.ThreadLocal` instance associates state with a thread. A non-`static` non-`final` `java.lang.ThreadLocal` field associates state with an instance-thread combination. This is seldom necessary and often a bug which can cause memory leaks and possibly incorrect behavior.

Here is an example of code that produces a violation:

``` groovy
private static ThreadLocal local1 = new ThreadLocal()
private final ThreadLocal local2 = new ThreadLocal()
protected ThreadLocal local3 = new ThreadLocal()
ThreadLocal local4 = new ThreadLocal()
```

## Further Reading

* [CodeNarc - ThreadLocalNotStaticFinal](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#ThreadLocalNotStaticFinal)