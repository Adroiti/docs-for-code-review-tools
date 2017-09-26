Pattern: Exception throw from `finally` block

Issue: -

## Description

Checks for throwing an exception from within a *finally* block. Throwing an exception from a *finally* block is confusing and can hide the original exception.

Here is an example of code that produces a violation:

``` groovy
int myMethod() {
    try {
        doSomething()
        throw new Exception()
    } finally {
        println 'finally'
        throw new Exception()   // violation
    }
}
```

## Further Reading

* [CodeNarc - ThrowExceptionFromFinallyBlock](http://codenarc.sourceforge.net/codenarc-rules-basic.html#ThrowExceptionFromFinallyBlock)