Pattern: Explicit call to `minus()`

Issue: -

## Description

This rule detects when the `minus(Object)` method is called directly in code instead of using the `-` operator. A groovier way to express this: `a.minus(b)` is this: `a - b`. This rule can be configured to ignore `minus.xor(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `minus(x)` will trigger a violation.

This rule also ignores all calls to `super.minus(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToMinusMethod](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitCallToMinusMethod)