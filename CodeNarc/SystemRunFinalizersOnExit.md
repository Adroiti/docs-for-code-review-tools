Pattern: Use of `System.runFinalizersOnExit()`

Issue: -

## Description

This method is inherently non-thread-safe, may result in data corruption, deadlock, and may affect parts of the program far removed from it's call point. It is deprecated, and it's use strongly discouraged.

Here is an example of code that produces a violation:

``` groovy
def method() {
    System.runFinalizersOnExit(true)
}
```

## Further Reading

* [CodeNarc - SystemRunFinalizersOnExit](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#systemrunfinalizersonexit-rule)