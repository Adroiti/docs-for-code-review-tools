Pattern: Catching `Throwable`

Issue: -

## Description

Checks for catching a `Throwable`. In most cases that is much too broad, and is also dangerous because it can catch exceptions such as `ThreadDeath` and `OutOfMemoryError`.

## Further Reading

* [CodeNarc - CatchThrowable](https://codenarc.github.io/CodeNarc/codenarc-rules-exceptions.html#catchthrowable-rule)