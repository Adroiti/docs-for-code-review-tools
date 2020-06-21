Pattern: Explicit call to `leftShift()`

Issue: -

## Description

This rule detects when the `leftShift(Object)` method is called directly in code instead of using the &lt;&lt; operator. A groovier way to express this: `a.leftShift(b)` is this: `a << b`. This rule can be configured to ignore `this.leftShift(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `leftShift(x)` will trigger a violation.

This rule also ignores all calls to `super.leftShift(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToLeftShiftMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#explicitcalltoleftshiftmethod-rule)