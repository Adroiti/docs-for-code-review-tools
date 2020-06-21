Pattern: `close()` without `Closeable`

Issue: -

## Description

If a class defines a `void close()` then that class should implement `java.io.Closeable`.

## Further Reading

* [CodeNarc - CloseWithoutCloseable](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#closewithoutcloseable-rule)