Pattern: Explicit call to `getAt()`

Issue: -

## Description

This rule detects when the `getAt(Object)` method is called directly in code instead of using the `[]` index operator. A groovier way to express this: `a.getAt(b)` is this: `a[b]`. This rule can be configured to ignore `this.getAt(Object)` using the *ignoreThisReference* property. It defaults to *false*, so even `getAt(x)` will trigger a violation.

This rule also ignores all calls to `super.getAt(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToGetAtMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#explicitcalltogetatmethod-rule)