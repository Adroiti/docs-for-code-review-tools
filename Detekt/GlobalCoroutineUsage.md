Pattern: Global coroutine usage

Issue: -

## Description

Report usages of `GlobalScope.launch` and `GlobalScope.async`. It is highly discouraged by the Kotlin documentation:
> Global scope is used to launch top-level coroutines which are operating on the whole application lifetime and are
> Application code usually should use an application-defined CoroutineScope. Using async or launch on the instance

Example of **incorrect** code:

```kotlin

Example of **correct** code:

```kotlin
fun foo() {
fun onDestroy() {

## Further Reading

* [Detekt - GlobalCoroutineUsage](https://arturbosch.github.io/detekt/coroutines.html#globalcoroutineusage)
* [kotlinx.coroutines](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines/-global-scope)