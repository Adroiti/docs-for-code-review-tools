Pattern: Unnecessary `null` check before `instanceof`

Issue: -

## Description

There is no need to check for `null` before an `instanceof`; the `instanceof` keyword returns false when given a `null` argument.

Example:

``` groovy
if (x != null && x instanceof MyClass) {
    // should drop the "x != null" check
}

if (x instanceof MyClass && x != null) {
    // should drop the "x != null" check
}

// should drop the "x != null" check
(x != null && x instanceof MyClass) ? foo : bar

if (x != null && x instanceof MyClass && x.isValid()) {
    // this is OK and causes no violation because the x.isValid() requires a non null reference
}
```

## Further Reading

* [CodeNarc - UnnecessaryNullCheckBeforeInstanceOf](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryNullCheckBeforeInstanceOf)