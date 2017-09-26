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

* [CodeNarc - SwallowThreadDeath](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#SwallowThreadDeath)