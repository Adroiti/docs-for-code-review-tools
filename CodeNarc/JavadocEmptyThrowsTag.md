Pattern: Empty `@throws` tag

Issue: -

## Description

Checks for empty `@throws` tag within javadoc. Known limitation: Only the first occurrence of an empty `@throws` within a javadoc comment is found.

Example of violations:

``` groovy
/**
 * Return the calculated count of some stuff.
 *
 * @param startIndex - the starting index
 * @return the count
 * @throws                                          // violation
 */
int countThings(int startIndex) { }
```

## Further Reading

* [CodeNarc - JavadocEmptyThrowsTag](https://codenarc.github.io/CodeNarc/codenarc-rules-comments.html#javadocemptythrowstag-rule)