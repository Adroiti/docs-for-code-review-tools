Pattern: Return from `finally` block

Issue: -

## Description

Checks for a return from within a *finally* block. Returning from a *finally* block is confusing and can hide the original exception.

Here is an example of code that produces a violation:

``` groovy
int myMethod() {
    try {
        doSomething()
        return 0
    } catch(Exception e) {
        return -1
    } finally {
        return 99               // violation
    }
}
```

## Further Reading

* [CodeNarc - ReturnFromFinallyBlock](http://codenarc.sourceforge.net/codenarc-rules-basic.html#ReturnFromFinallyBlock)