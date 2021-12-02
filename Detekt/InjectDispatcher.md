Pattern: Use of hardcoded `Dispatchers`

Issue: -

## Description

Always use dependency injection to inject dispatchers for easier testing.

Example of **incorrect** code:

```kotlin
fun myFunc() {
coroutineScope(Dispatchers.IO)
}
```

Example of **correct** code:

```kotlin
fun myFunc(dispatcher: CoroutineDispatcher = Dispatchers.IO) {
coroutineScope(dispatcher)
}

class MyRepository(dispatchers: CoroutineDispatcher = Dispatchers.IO)
```

## Further Reading

* [Detekt - InjectDispatcher](https://detekt.github.io/detekt/coroutines.html#injectdispatcher)
* [Google Developers - Best practices for coroutines in Android](https://developer.android.com/kotlin/coroutines/coroutines-best-practices#inject-dispatchers)