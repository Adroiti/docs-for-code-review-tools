Pattern: Catching `NullPointerException`

Issue: -

## Description

Checks for catching a `NullPointerException`. Catching `NullPointerException` is never appropriate. It should be avoided in the first place with proper null checking, and it can mask underlying errors.

## Further Reading

* [CodeNarc - CatchNullPointerException](https://codenarc.github.io/CodeNarc/codenarc-rules-exceptions.html#catchnullpointerexception-rule)