Pattern: Explicit call to `equals()`

Issue: -

## Description

This rule detects when the `equals(Object)` method is called directly in code instead of using the `==` or `!=` operator. A groovier way to express this: `a.equals(b)` is this: `a == b` and a groovier way to express : `!a.equals(b)` is: `a != b`. This rule can be configured to ignore `this.equals(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `equals(x)` will trigger a violation.

This rule also ignores all calls to `super.equals(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToEqualsMethod](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitCallToEqualsMethod)