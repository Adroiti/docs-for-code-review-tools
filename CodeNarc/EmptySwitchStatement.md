Pattern: Empty `switch` statement

Issue: -

## Description

Checks for empty *switch* statements. Empty *switch* statements are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def myMethod() {
    switch(myVariable) {
        // empty
    }
}
```

## Further Reading

* [CodeNarc - EmptySwitchStatement](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptySwitchStatement)