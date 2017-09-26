Pattern: Use of `Thread.yield()`

Issue: -

## Description

This rule reports uses of the `Thread.yield()` method.

Method calls to `Thread.yield()` should not be allowed. This method has no useful guaranteed semantics, and is often used by inexperienced programmers to mask race conditions.

Here is an example of code that produces a violation:

``` groovy
 def method() {
     Thread.yield()
 }
```

## Further Reading

* [CodeNarc - ThreadYield](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#ThreadYield)