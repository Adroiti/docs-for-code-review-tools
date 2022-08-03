Pattern: `suspend` function uses `CoroutineScope` as receiver

Issue: -

## Description

Suspend functions that use `CoroutineScope` as receiver should not be marked as `suspend`.
A `CoroutineScope` provides structured concurrency via its `coroutineContext`. A `suspend`
function also has its own `coroutineContext`, which is now ambiguous and mixed with the
receiver`s.

Example of **incorrect** code:

```kotlin
suspend fun CoroutineScope.foo() {
    launch {
      delay(1.seconds)
    }
}
```

Example of **correct** code:

```kotlin
fun CoroutineScope.foo() {
    launch {
      delay(1.seconds)
    }
}

// Alternative
suspend fun foo() = coroutineScope {
    launch {
      delay(1.seconds)
    }
}
```

## Further Reading

* [Detekt - SuspendFunWithCoroutineScopeReceiver](https://detekt.dev/docs/rules/coroutines/#suspendfunwithcoroutinescopereceiver)