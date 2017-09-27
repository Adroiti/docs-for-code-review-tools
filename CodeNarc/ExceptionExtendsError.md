Pattern: Exception extends `Error`

Issue: -

## Description

Errors are system exceptions. Do not extend them.

Examples:

``` groovy
class SomeError extends Error { }  // violation
class SomeError extends java.lang.Error { }  // violation

class SomeException extends Exception { }  // OK
```

## Further Reading

* [CodeNarc - ExceptionExtendsError](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#ExceptionExtendsError)