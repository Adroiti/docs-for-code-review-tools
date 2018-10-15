Pattern: Use of non-text encoding for `str.encode`/`str.decode`

Issue: -

## Description

`str.encode` or `str.decode` is called with a non-text encoding. Use `codecs` module to handle arbitrary codecs.

## Further Reading

* [The Python Standard Library - Codec registry and base classes](https://docs.python.org/3/library/codecs.html)
