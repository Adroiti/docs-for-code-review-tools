Pattern: Return of `null` instead of empty array

Issue: -

## Description

If you have a method or closure that returns an array, then when there are no results return a zero-length (empty) array rather than `null`. It is often a better design to return a zero-length array rather than a `null` reference to indicate that there are no results (i.e., an *empty* list of results). This way, no explicit check for `null` is needed by clients of the method.

## Further Reading

* [CodeNarc - ReturnsNullInsteadOfEmptyArray](http://codenarc.sourceforge.net/codenarc-rules-design.html#ReturnsNullInsteadOfEmptyArray)