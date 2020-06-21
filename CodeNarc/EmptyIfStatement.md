Pattern: Empty `if` statement

Issue: -

## Description

Checks for empty *if* statements. Empty *if* statements are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def someMethod() {
    if (x==23) {
        // empty
    }
}
```

## Further Reading

* [CodeNarc - EmptyIfStatement](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#emptyifstatement-rule)