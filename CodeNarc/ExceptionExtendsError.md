Pattern: Exception extends `Error`

Issue: -

## Description

Errors are system exceptions. Do not extend them.

Examples:

``` groovy
class MyError extends Error { }  // violation
class MyError extends java.lang.Error { }  // violation

class MyException extends Exception { }  // OK
```

## Further Reading

* [CodeNarc - ExceptionExtendsError](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#ExceptionExtendsError)