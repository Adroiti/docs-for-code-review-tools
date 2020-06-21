Pattern: Empty `for` statement

Issue: -

## Description

Checks for empty *for* blocks. Empty *for* statements are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def someMethod() {
    for (int i=0; i < 23; i++) {
        // empty
    }
}
```

## Further Reading

* [CodeNarc - EmptyForStatement](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#emptyforstatement-rule)