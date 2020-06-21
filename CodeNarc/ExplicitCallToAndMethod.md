Pattern: Explicit call to `and()`

Issue: -

## Description

This rule detects when the `and(Object)` method is called directly in code instead of using the `&` operator. A groovier way to express this: `a.and(b)` is this: `a & b`. This rule can be configured to ignore `this.and(Object)` using the *ignoreThisReference* property. It defaults to *true*, so even `and(x)` will not trigger a violation. The default is *true* because `and` appears commonly in Grails criteria.

This rule also ignores all calls to `super.and(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToAndMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#explicitcalltoandmethod-rule)