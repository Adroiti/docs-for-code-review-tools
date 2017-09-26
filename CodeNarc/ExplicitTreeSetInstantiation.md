Pattern: Explicit `TreeSet` instantiation

Issue: -

## Description

This rule checks for explicit calls to the no-argument constructor of `TreeSet`. In Groovy, it is best to replace `new TreeSet()` with `[] as SortedSet`, which creates the same object.

## Further Reading

* [CodeNarc - ExplicitTreeSetInstantiation](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitTreeSetInstantiation)