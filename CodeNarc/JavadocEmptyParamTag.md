Pattern: Empty `@param` tag

Issue: -

## Description

Checks for empty `@param` tags within javadoc. Known limitation: Only the first occurrence of an empty `@param` within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param                                               // violation
 * @return the full count
 * @throws RuntimeException
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocEmptyParamTag](http://codenarc.sourceforge.net/codenarc-rules-comments.html#JavadocEmptyParamTag)