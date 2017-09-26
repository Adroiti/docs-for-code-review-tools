Pattern: Explicit call to `plus()`

Issue: -

## Description

This rule detects when the `plus(Object)` method is called directly in code instead of using the `+` operator. A groovier way to express this: `a.plus(b)` is this: `a + b`. This rule can be configured to ignore `this.plus(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `plus(x)` will trigger a violation.

This rule also ignores all calls to `super.plus(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToPlusMethod](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitCallToPlusMethod)