Pattern: Object extends `Throwable`

Issue: -

## Description

Throwable instances are not intended for reuse as they are stateful and contain mutable information about a specific exception or error. Hence, global singleton `Throwables` should be avoided.

Example of **incorrect** code:

```java
object InvalidCredentialsException : Throwable()

object BanException : Exception()

object AuthException : RuntimeException()
```

Example of **correct** code:

```java
class InvalidCredentialsException : Throwable()

class BanException : Exception()

class AuthException : RuntimeException()
```

## Further Reading

* [Detekt - ObjectExtendsThrowable](https://detekt.dev/docs/rules/exceptions/#objectextendsthrowable)