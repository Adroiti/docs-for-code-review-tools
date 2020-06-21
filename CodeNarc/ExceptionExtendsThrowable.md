Pattern: Exception extends `Throwable`

Issue: -

## Description

Checks for classes that extend `Throwable`. Custom exception classes should subclass `Exception` or one of its descendants.

Example of violations:

``` groovy
class SomeException extends Throwable { }   // violation
```

## Further Reading

* [CodeNarc - ExceptionExtendsThrowable](https://codenarc.github.io/CodeNarc/codenarc-rules-exceptions.html#exceptionextendsthrowable-rule)