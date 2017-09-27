Pattern: Unnecessary `String.substring(0)`

Issue: -

## Description

Calling `String.substring(0)` always returns the original string. This code is meaningless.

Examples:

``` groovy
string.substring(0)         // violation
method().substring(0)       // violation

prop.substring(1)           // OK, not constant 0
prop.substring(0, 1)        // OK, end is specified
```

## Further Reading

* [CodeNarc - UnnecessaryCallToSubstring](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryCallToSubstring)