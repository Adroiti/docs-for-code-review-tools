Pattern: Unnecessary `Boolean` instantiation

Issue: -

## Description

Checks for direct call to a `Boolean` constructor. Use `Boolean.valueOf()` or the `Boolean.TRUE` and `Boolean.FALSE` constants instead of calling the `Boolean()` constructor directly.

Also checks for `Boolean.valueOf(true)` or `Boolean.valueOf(false)`. Use the `Boolean.TRUE` or `Boolean.FALSE` constants instead.

Here is an example of code that produces a violation:

``` groovy
def b1 = new Boolean(true)             // violation
def b2 = new java.lang.Boolean(false)  // violation
def b3 = Boolean.valueOf(true)         // violation
def b4 = Boolean.valueOf(false)        // violation
```

## Further Reading

* [CodeNarc - UnnecessaryBooleanInstantiation](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryBooleanInstantiation)