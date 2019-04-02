Pattern: Explicit call to _Garbage Collector_

Issue: -

## Description

Reports all calls to explicitly trigger the _Garbage Collector_. Code should work independently of the garbage collector and should not require the GC to be triggered in certain points in time.

Example of **incorrect** code:

```kotlin
System.gc()
Runtime.getRuntime().gc()
System.runFinalization()
```

## Further Reading

* [Detekt - ExplicitGarbageCollectionCall](https://arturbosch.github.io/detekt/potential-bugs.html#explicitgarbagecollectioncall)