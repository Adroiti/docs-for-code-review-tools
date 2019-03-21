Pattern: Empty `@author` tag

Issue: -

## Description

Checks for empty `@author` tags within javadoc. Known limitation: Only the first occurrence of an empty `@author` within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex - the starting index
 * @return the count
 * @author                                             // violation
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocEmptyAuthorTag](http://codenarc.sourceforge.net/codenarc-rules-comments.html#JavadocEmptyAuthorTag)