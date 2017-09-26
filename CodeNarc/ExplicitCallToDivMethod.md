Pattern: Explicit call to `div()`

Issue: -

## Description

This rule detects when the `div(Object)` method is called directly in code instead of using the `/` operator. A groovier way to express this: `a.div(b)` is this: `a / b`. This rule can be configured to ignore `div.xor(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `div(x)` will trigger a violation.

This rule also ignores all calls to `super.div(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToDivMethod](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitCallToDivMethod)