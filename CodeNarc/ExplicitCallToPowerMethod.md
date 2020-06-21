Pattern: Explicit call to `power()`

Issue: -

## Description

This rule detects when the `power(Object)` method is called directly in code instead of using the `**` operator. A groovier way to express this: `a.power(b)` is this: `a ** b`. This rule can be configured to ignore `this.power(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `power(x)` will trigger a violation.

This rule also ignores all calls to `super.power(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToPowerMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#explicitcalltopowermethod-rule)