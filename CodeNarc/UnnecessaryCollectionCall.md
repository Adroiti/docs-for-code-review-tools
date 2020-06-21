Pattern: Unnecessary collection call

Issue: -

## Description

Checks for useless calls to collections. For any collection `c`, calling `c.containsAll(c)` should always be `true`, and `c.retainAll(c)` should have no effect.

## Further Reading

* [CodeNarc - UnnecessaryCollectionCall](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarycollectioncall-rule)