Pattern: Throwing instance of `Error`

Issue: -

## Description

Checks for throwing an instance of `java.lang.Error`. This is not appropriate within normal application code. Throw an instance of a more specific exception subclass instead.

## Further Reading

* [CodeNarc - ThrowError](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#ThrowError)