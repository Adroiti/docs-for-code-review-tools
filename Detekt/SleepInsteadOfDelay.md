Pattern: Use of `Thread.sleep` instead of `delay`

Issue: -

## Description

A thread can contain multiple coroutines at one time due to coroutines’ lightweight nature, so if one coroutine invokes `Thread.sleep`, it could potentially halt the execution of unrelated coroutines and cause unpredictable behavior.

Example of **incorrect** code:

```java
suspend fun foo() {
    Thread.sleep(1_000L)
}
```

Example of **correct** code:

```java
suspend fun foo() {
    delay(1_000L)
}
```

## Further Reading

* [Detekt - SleepInsteadOfDelay](https://detekt.dev/docs/rules/coroutines/#sleepinsteadofdelay)