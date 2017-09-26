Pattern: Explicit `Stack` instantiation

Issue: -

## Description

This rule checks for explicit calls to the no-argument constructor of `Stack`. In Groovy, it is best to replace `new Stack()` with `[] as Stack`, which creates the same object.

## Further Reading

* [CodeNarc - ExplicitStackInstantiation](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitStackInstantiation)