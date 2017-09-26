Pattern: Empty `try` block

Issue: -

## Description

Checks for empty *try* blocks. Empty *try* blocks are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def myMethod() {
    try {
        // empty
    } catch(MyException e) {
        e.printStackTrace()
    }
}
```

## Further Reading

* [CodeNarc - EmptyTryBlock](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptyTryBlock)