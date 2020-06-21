Pattern: Exception throw from `finally` block

Issue: -

## Description

Checks for throwing an exception from within a *finally* block. Throwing an exception from a *finally* block is confusing and can hide the original exception.

Here is an example of code that produces a violation:

``` groovy
int someMethod() {
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

* [CodeNarc - ThrowExceptionFromFinallyBlock](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#throwexceptionfromfinallyblock-rule)