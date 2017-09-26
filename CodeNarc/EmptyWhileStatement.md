Pattern: Empty `while` statement

Issue: -

## Description

Checks for empty *while* statements. Empty *while* statements are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def myMethod() {
    while (!stopped) {
        // empty
    }
}
```

## Further Reading

* [CodeNarc - Empty `while` statement](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptyWhileStatement)