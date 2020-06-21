Pattern: Assert within `finally` block

Issue: -

## Description

Checks for *assert* statements within a *finally* block. An *assert* can throw an exception, hiding the original exception, if there is one.

Here is an example of code that produces a violation:

``` groovy
int someMethod(int count) {
    try {
        doSomething()
    } finally {
        assert count > 0        // violation
    }
}
```

## Further Reading

* [CodeNarc - AssertWithinFinallyBlock](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#assertwithinfinallyblock-rule)