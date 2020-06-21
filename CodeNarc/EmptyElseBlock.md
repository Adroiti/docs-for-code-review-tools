Pattern: Empty `else` block

Issue: -

## Description

Checks for empty *else* blocks. Empty *else* blocks are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def someMethod() {
    if (x==23) {
        println 'ok'
    } else {
        // empty
    }
}
```

## Further Reading

* [CodeNarc - EmptyElseBlock](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#emptyelseblock-rule)