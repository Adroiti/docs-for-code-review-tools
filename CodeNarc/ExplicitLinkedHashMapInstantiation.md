Pattern: Explicit `LinkedHashMap` instantiation

Issue: -

## Description

This rule checks for the explicit instantiation of a `LinkedHashMap` using the no-arg constructor. In Groovy, it is best to replace `new LinkedHashMap()` with `[:]`, which creates the same object.

## Further Reading

* [CodeNarc - ExplicitLinkedHashMapInstantiation](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#explicitlinkedhashmapinstantiation-rule)