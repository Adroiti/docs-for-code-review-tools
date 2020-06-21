Pattern: Catching `Error`

Issue: -

## Description

Checks for catching a `Error`. In most cases that is much too broad, and is also dangerous because it can catch exceptions such as `ThreadDeath` and `OutOfMemoryError`.

## Further Reading

* [CodeNarc - CatchError](https://codenarc.github.io/CodeNarc/codenarc-rules-exceptions.html#catcherror-rule)