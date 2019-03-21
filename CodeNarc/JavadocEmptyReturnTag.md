Pattern: Empty `@return` tag

Issue: -

## Description

Checks for empty `@return` tags within javadoc. Known limitation: Only the first occurrence of an empty `@return` within a
javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex - the starting index
 * @return                                  // violation
 * @throws RuntimeException
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocEmptyReturnTag](http://codenarc.sourceforge.net/codenarc-rules-comments.html#JavadocEmptyReturnTag)