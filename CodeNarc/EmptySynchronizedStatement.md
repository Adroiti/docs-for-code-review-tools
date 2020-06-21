Pattern: Empty `synchronized` statement

Issue: -

## Description

Checks for empty *synchronized* statements. Empty *synchronized* statements are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
class SomeClass {
    def someMethod() {
        synchronized(lock) {
        }
    }
}
```

## Further Reading

* [CodeNarc - EmptySynchronizedStatement](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#emptysynchronizedstatement-rule)