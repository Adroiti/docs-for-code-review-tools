Pattern: Use of `removeAll()`

Issue: -

## Description

Don't use `removeAll` to clear a collection. If you want to remove all elements from a collection `c`, use `c.clear`, not `c.removeAll(c)`. Calling `c.removeAll(c)` to clear a collection is less clear, susceptible to errors from typos, less efficient and for some collections, might throw a `ConcurrentModificationException`.

## Further Reading

* [CodeNarc - RemoveAllOnSelf](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#removeallonself-rule)