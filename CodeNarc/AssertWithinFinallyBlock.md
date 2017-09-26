Pattern: Assert within `finally` block

Issue: -

## Description

Checks for *assert* statements within a *finally* block. An *assert* can throw an exception, hiding the original exception, if there is one.

Here is an example of code that produces a violation:

``` groovy
int myMethod(int count) {
    try {
        doSomething()
    } finally {
        assert count > 0        // violation
    }
}
```

## Further Reading

* [CodeNarc - AssertWithinFinallyBlock](http://codenarc.sourceforge.net/codenarc-rules-basic.html#AssertWithinFinallyBlock)