Pattern: Global coroutine usage

Issue: -

## Description

Report usages of `GlobalScope.launch` and `GlobalScope.async`. It is highly discouraged by the Kotlin documentation:
> Global scope is used to launch top-level coroutines which are operating on the whole application lifetime and are> not cancelled prematurely.
> Application code usually should use an application-defined CoroutineScope. Using async or launch on the instance> of GlobalScope is highly discouraged.

Example of **incorrect** code:

```kotlinfun foo() {    GlobalScope.launch { delay(1_000L) }}```

Example of **correct** code:

```kotlinval scope = CoroutineScope(Dispatchers.Default)
fun foo() {    scope.launch { delay(1_000L) }}
fun onDestroy() {   scope.cancel()}```

## Further Reading

* [Detekt - GlobalCoroutineUsage](https://detekt.github.io/detekt/coroutines.html#globalcoroutineusage)
* [kotlinx.coroutines](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines/-global-scope)