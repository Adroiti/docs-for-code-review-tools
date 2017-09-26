Pattern: Empty `catch` block

Issue: -

## Description

Checks for empty *catch* blocks. In most cases, exceptions should not be caught and ignored (swallowed).

The rule has a property named `ignoreRegex` that defaults to the value `ignore|ignored`. If the name of the exception matches this regex then no violations are produced.

Examples:

``` groovy
def myMethod() {
    try {
        doSomething
    } catch(MyException e) {                //violation
        // should do something here
    }
}

def myMethod() {
    try {
        doSomething
    } catch(MyException ignored) {
        //no violations because the parameter name is ignored
    }
}
```

## Further Reading

* [CodeNarc - EmptyCatchBlock](http://codenarc.sourceforge.net/codenarc-rules-basic.html#EmptyCatchBlock)