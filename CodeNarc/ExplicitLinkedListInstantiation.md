Pattern: Explicit `LinkedList` instantiation

Issue: -

## Description

This rule checks for explicit calls to the no-argument constructor of `LinkedList`. In Groovy, it is best to replace `new LinkedList()` with `[] as Queue`, which creates the same object.

## Further Reading

* [CodeNarc - ExplicitLinkedListInstantiation](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitLinkedListInstantiation)