Pattern: Explicit call to `rightShift()`

Issue: -

## Description

This rule detects when the `rightShift(Object)` method is called directly in code instead of using the &gt;&gt; operator. A groovier way to express this: `a.rightShift(b)` is this: `a >> b`. This rule can be configured to ignore `this.rightShift(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `rightShift(x)` will trigger a violation.

This rule also ignores all calls to `super.rightShift(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToRightShiftMethod](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitCallToRightShiftMethod)