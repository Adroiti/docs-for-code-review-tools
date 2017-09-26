Pattern: Exception extends `Throwable`

Issue: -

## Description

Checks for classes that extend `Throwable`. Custom exception classes should subclass `Exception` or one of its descendants.

Example of violations:

``` groovy
class MyException extends Throwable { }   // violation
```

## Further Reading

* [CodeNarc - ExceptionExtendsThrowable](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#ExceptionExtendsThrowable)