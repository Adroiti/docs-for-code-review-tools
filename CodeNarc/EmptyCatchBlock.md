Pattern: Empty `catch` block

Issue: -

## Description

Checks for empty *catch* blocks. In most cases, exceptions should not be caught and ignored (swallowed).

The rule has a property named `ignoreRegex` that defaults to the value `ignore|ignored`. If the name of the exception matches this regex then no violations are produced.

Examples:

``` groovy
def someMethod() {
    try {
        doSomething
    } catch(SomeException e) {                //violation
        // should do something here
    }
}

def someMethod() {
    try {
        doSomething
    } catch(SomeException ignored) {
        //no violations because the parameter name is ignored
    }
}
```

## Further Reading

* [CodeNarc - EmptyCatchBlock](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#emptycatchblock-rule)