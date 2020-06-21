Pattern: Use of `ThreadGroup`

Issue: -

## Description

Although it is intended to be used in a threaded environment, `ThreadGroup` contains methods that are not thread safe.

Here is an example of code that produces a violation:

``` groovy
new ThreadGroup("...")
new ThreadGroup(tg, "thread group")
Thread.currentThread().getThreadGroup()
System.getSecurityManager().getThreadGroup()
```

## Further Reading

* [CodeNarc - ThreadGroup](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#threadgroup-rule)