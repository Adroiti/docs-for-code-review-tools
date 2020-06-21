Pattern: Call to `finalize()`

Issue: -

## Description

The `finalize()` method should only be called by the JVM after the object has been garbage collected.

While the Java Language Specification allows an object's `finalize()` method to be called from outside the finalizer, doing so is usually a bad idea. For example, calling `finalize()` explicitly means that `finalize()` will be called more than once: the first time will be the explicit call and the last time will be the call that is made after the object is garbage collected.

## Further Reading

* [CodeNarc - ObjectFinalize](https://codenarc.github.io/CodeNarc/codenarc-rules-security.html#objectfinalize-rule)