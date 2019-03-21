Pattern: Empty `@exception` tag

Issue: -

## Description

Checks for empty `@exception` tags within javadoc. Known limitation: Only the first occurrence of an empty `@exception` within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex - the starting index
 * @return the count
 * @exception                                           // violation
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocEmptyExceptionTag](http://codenarc.sourceforge.net/codenarc-rules-comments.html#JavadocEmptyExceptionTag)