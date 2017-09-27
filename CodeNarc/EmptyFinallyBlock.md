Pattern: Empty `finally` block

Issue: -

## Description

Checks for empty *finally* blocks. Empty *finally* blocks are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def someMethod() {
    try {
        doSomething()
    } finally {
        // empty
    }
}
```

## Further Reading

* [CodeNarc - EmptyFinallyBlock](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptyFinallyBlock)