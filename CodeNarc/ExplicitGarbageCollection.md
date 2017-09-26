Pattern: Explicit garbage collection

Issue: -

## Description

Calls to `System.gc()`, `Runtime.getRuntime().gc()`, and `System.runFinalization()` are not advised. Code should have the same behavior whether the garbage collection is disabled using the option `-Xdisableexplicitgc` or not. Moreover, "modern" JVMs do a very good job handling garbage collections. If memory usage issues unrelated to memory leaks develop within an application, it should be dealt with JVM options rather than within the code itself.

## Further Reading

* [CodeNarc - ExplicitGarbageCollection](http://codenarc.sourceforge.net/codenarc-rules-basic.html#ExplicitGarbageCollection)