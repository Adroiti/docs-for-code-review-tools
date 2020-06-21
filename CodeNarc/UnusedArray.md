Pattern: Unused array

Issue: -

## Description

Checks for array allocations that are not assigned or used, unless it is the last statement within a block (because it may be the intentional return value). Examples include:

``` groovy
int someMethod() {
    new String[3]               // unused
    return -1
}

String[] someMethod() {
    new String[3]               // OK (last statement in block)
}

def closure = {
    doStuff()
    new Date[3]                 // unused
    doOtherStuff()
}

def closure = { new Date[3] }   // OK (last statement in block)
```

## Further Reading

* [CodeNarc - UnusedArray](https://codenarc.github.io/CodeNarc/codenarc-rules-unused.html#unusedarray-rule)