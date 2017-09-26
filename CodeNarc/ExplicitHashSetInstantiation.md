Pattern: Explicit `HashSet` instantiation

Issue: -

## Description

This rule checks for explicit calls to the no-argument constructor of `HashSet`. In Groovy, it is best to replace `new HashSet()` with `[] as Set`, which creates the same object.

## Further Reading

* [CodeNarc - ExplicitHashSetInstantiation](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitHashSetInstantiation)