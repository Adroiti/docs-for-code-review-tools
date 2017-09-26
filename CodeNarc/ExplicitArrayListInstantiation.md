Pattern: Explicit `ArrayList` instantiation

Issue: -

## Description

This rule checks for explicit calls to the no-argument constructor of `ArrayList`. In Groovy, it is best to write `new ArrayList() as []`, which creates the same object.

## Further Reading

* [CodeNarc - ExplicitArrayListInstantiation](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitArrayListInstantiation)