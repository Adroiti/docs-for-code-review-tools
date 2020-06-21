Pattern: `ThreadDeath` without re-throw

Issue: -

## Description

Detects code that catches `java.lang.ThreadDeath` without re-throwing it.

Example of violations:

``` groovy
try {
    def a = 0
} catch (ThreadDeath td) {
    td.printStackTrace()
}
```

## Further Reading

* [CodeNarc - SwallowThreadDeath](https://codenarc.github.io/CodeNarc/codenarc-rules-exceptions.html#swallowthreaddeath-rule)