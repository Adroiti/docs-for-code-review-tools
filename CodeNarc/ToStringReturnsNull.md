Pattern: `toString()` returns `null`

Issue: -

## Description

Checks for `toString()` methods that return `null`. This is unconventional and could cause unexpected `NullPointerExceptions` from normal or implicit use of `toString()`.

Example of violations:

``` groovy
class SomeClass {
    String toString() {
        if (foo()) {
            return 'SomeClass'
        } else {
            return null         // violation
        }
    }
}

class SomeClass {
    String toString() {
        calculateStuff()
        null                    // violation
    }
}

class SomeClass {
    String toString() {         // violation - implicit return of null
    }
}
```

## Further Reading

* [CodeNarc - ToStringReturnsNull](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#tostringreturnsnull-rule)