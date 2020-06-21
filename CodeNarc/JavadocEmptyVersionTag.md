Pattern: Empty `@version` tag

Issue: -

## Description

Checks for empty `@version` tags within javadoc. Known limitation: Only the first occurrence of an empty `@version` within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex - the starting index
 * @return the count
 * @version                                          // violation
 */
```

## Further Reading

* [CodeNarc - JavadocEmptyVersionTag](https://codenarc.github.io/CodeNarc/codenarc-rules-comments.html#javadocemptyversiontag-rule)