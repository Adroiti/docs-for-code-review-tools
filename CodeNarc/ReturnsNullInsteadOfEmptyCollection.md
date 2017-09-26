Pattern: Return of `null` instead of empty collection

Issue: -

## Description

If you have a method or closure that returns a collection, then when there are no results return a zero-length (empty) collection rather than `null`. It is often a better design to return a zero-length collection rather than a `null` reference to indicate that there are no results (i.e., an *empty* list of results). This way, no explicit check for `null` is needed by clients of the method.

## Further Reading

* [CodeNarc - ReturnsNullInsteadOfEmptyCollection](http://codenarc.sourceforge.net/codenarc-rules-design.html#ReturnsNullInsteadOfEmptyCollection)