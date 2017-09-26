Pattern: Explicit call to `xor()`

Issue: -

## Description

This rule detects when the `xor(Object)` method is called directly in code instead of using the `^` operator. A groovier way to express this: `a.xor(b)` is this: `a ^ b`. This rule can be configured to ignore `this.xor(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `xor(x)` will trigger a violation.

This rule also ignores all calls to `super.xor(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToXorMethod](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitCallToXorMethod)