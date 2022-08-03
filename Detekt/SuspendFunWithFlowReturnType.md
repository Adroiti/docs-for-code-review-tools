Pattern: Use of `suspend` with `Flow` return type

Issue: -

## Description

Functions that return `Flow` from `kotlinx.coroutines.flow` should not be marked as `suspend`. `Flows` are intended to be cold observable streams. The act of simply invoking a function that returns a `Flow`, should not have any side effects. Only once collection begins against the returned `Flow`, should work actually be done.


Example of **incorrect** code:

```kotlin
suspend fun observeSignals(): Flow<Unit> {
    val pollingInterval = getPollingInterval() // Done outside of the flow builder block.
    return flow {
        while (true) {
            delay(pollingInterval)
            emit(Unit)
        }
    }
}

private suspend fun getPollingInterval(): Long {
    // Return the polling interval from some repository
    // in a suspending manner.
}
```

Example of **correct** code:

```kotlin
fun observeSignals(): Flow<Unit> {
    return flow {
        val pollingInterval = getPollingInterval() // Moved into the flow builder block.
        while (true) {
            delay(pollingInterval)
            emit(Unit)
        }
    }
}

private suspend fun getPollingInterval(): Long {
    // Return the polling interval from some repository
    // in a suspending manner.
}
```

## Further Reading

* [Detekt - SuspendFunWithFlowReturnType](https://detekt.dev/docs/rules/coroutines/#suspendfunwithflowreturntype)