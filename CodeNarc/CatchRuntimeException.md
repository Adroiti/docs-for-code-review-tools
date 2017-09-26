Pattern: Catching `RuntimeException`

Issue: -

## Description

Checks for catching a `RuntimeException`. In most cases that is too broad or general. It should usually be restricted to framework or infrastructure code, rather than application code.

## Further Reading

* [CodeNarc - CatchRuntimeException](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#CatchRuntimeException)