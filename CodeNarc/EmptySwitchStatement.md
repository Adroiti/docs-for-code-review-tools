Pattern: Empty `switch` statement

Issue: -

## Description

Checks for empty *switch* statements. Empty *switch* statements are confusing and serve no purpose.

Here is an example of code that produces a violation:

``` groovy
def someMethod() {
    switch(someVariable) {
        // empty
    }
}
```

## Further Reading

* [CodeNarc - EmptySwitchStatement](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#emptyswitchstatement-rule)